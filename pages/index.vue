<template>
  <section class="container">
    <div>
      <p>{{ msg }}</p>
      <br>Login:
      <b-input v-model="login"></b-input>
      <br>Password:
      <b-input v-model="password" type="password"></b-input>
<!--      <br>Spawn link below only if user already register<br> -->
      <nuxt-link class="nav-link" to="/game">Game</nuxt-link>

      <b-button @click="Reqest('')">INDEX</b-button>
      <b-button @click="Login">Login</b-button>
      <b-button @click="Reqest('logout')">Log out</b-button>
      <!-- <br><br> -->
      <!-- <b-button @click="socketConnect">Socket connect</b-button>
      <b-button @click="socketMsg">Socket test msg</b-button>
      <b-button @click="disconnectSocket">Disconnect socket</b-button> -->
    </div>
  </section>
</template>

<script>
import Logo from "~/components/Logo.vue";
import io from "~/plugins/socket.io.js";
import Axios from "axios";

export default {
  components: {
    Logo
  },
  data() {
    return {
      login: "calemb@gmail.com",
      password: "1234",
      msg: "",
      ip: "http://127.0.0.1:3000/",
      socket: undefined
    };
  },
  methods: {
    Login: function() {
      var that = this;
      Axios.post(
        this.ip + "login",
        {
          email: this.login,
          password: this.password,
        },
        {
          withCredentials: true
        }
      ).then(response => {
        this.msg = response.data.location + response.status;
        window.location = response.data.location;
      });
    },
    Reqest: function(page) {
      var that = this;
      Axios.get(this.ip + page, { withCredentials: true }) //withcredentials allow to set cookies from server side!!!!
        .then(response => {
          that.msg =
            JSON.stringify(response.data.data) +
            " :::: MAIL(session): " +
            response.data.mail;
          // document.cookie = response.cookie
        })
        .catch(error => {
          console.log(error);
          that.msg = error;
        })
        .finally(() => {
          // that.debugMsg = 'Final catch!'
          console.log("finally ping index");
        });
    },
    socketConnect: function() {
      this.socket = io("ws://127.0.01:3000");
      // this.socket.connect();
      // io.emit("login", function(messages) {
      //   callback(null, {
      //     messages,
      //     message: ""
      //   });
      // });
      this.msg =
        "Should test if socket response properly: allow only few requests without login, and allow much more with sockets!";
    },
    socketMsg: function() {
      if (typeof this.socket !== "undefined") {
        this.socket.emit("msg", "test msg content", function(data) {
          // args are sent in order to acknowledgement function
          console.log(data); // data will be 'tobi says woot'
        });
        console.log("tried to emit!");
      } else {
        console.log("socket is undefined!");
      }
    },
    disconnectSocket: function() {
      this.socket.disconnect();
    }
  }
};
</script>

<style>
body {

  background-color: #000;
}
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family: "Quicksand", "Source Sans Pro", -apple-system, BlinkMacSystemFont,
    "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}
</style>
