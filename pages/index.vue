<template>
  <section class="container">
    <div>
      <p>{{ msg }}</p>
      <br>Login:
      <b-input v-model="login"></b-input>
      <br>Password:
      <b-input v-model="password" type="password"></b-input>
      <b-button @click="Reqest('login')">Login</b-button>
      <b-button @click="Reqest('')">INDEX</b-button>
      <b-button @click="Reqest('logout')">Log out</b-button>
      <br>
      <b-button @click="socketTestAction">Test normal socket</b-button>
      <b-button @click="socketTestAction">Test restricted socket</b-button>
    </div>
  </section>
</template>

<script>
import Logo from "~/components/Logo.vue";
import Axios from "axios";

export default {
  components: {
    Logo
  },
  data() {
    return {
      login: "",
      password: "",
      msg: "",
      ip: "http://localhost:3000/"
    };
  },
  methods: {
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
    socketTestAction: function() {
      this.msg =
        "Should test if socket response properly: allow only few requests without login, and allow much more with sockets!";
    }
  }
};
</script>

<style>
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
