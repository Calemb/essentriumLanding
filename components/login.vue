<template>
  <div>
    <b-input
      v-model="login"
      type="text"
    ></b-input>

    <b-input
      v-model="password"
      type="password"
    ></b-input>
    <!--      <br>Spawn link below only if user already register<br> -->
    <!-- <nuxt-link class="nav-link" to="/game">Game</nuxt-link> -->
    <button
      @click="Login"
      class="btn btn-color"
    >Login</button>
  </div>
</template>

<script>
// import io from "~/plugins/socket.io.js";
import Axios from "axios";
import config from "~/local_modules/config";

export default {
  data () {
    return {
      login: "",
      password: "",
      msg: "",
      ip: config.ip,
      socket: undefined
    };
  },
  methods: {
    Login: function () {
      var that = this;
      Axios.post(
        this.ip + "login",
        {
          email: this.login,
          password: this.password
        },
        {
          withCredentials: true
        }
      )
        .then(response => {
          this.msg = response.data.location + response.status;
          if (typeof response.data.location !== "undefined") {
            setTimeout(() => {
              window.location = response.data.location;
            }, 5000);
          }
        })
        .catch(reason => {
          this.msg = reason;
        });
    },
    Reqest: function (page) {
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
    }
  }
};
</script>

<style scoped>
div {
  padding: 0px;
}
div input {
  font-size: 0.8em;
  display: inline-block;
  width: 80px;
  margin: 0px;
}
</style>
