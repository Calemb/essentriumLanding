<template>
  <div id="app">
    <div id="content">
      <b-navbar
        toggleable="lg"
        type="dark"
      >
        <login class="loginForm loginForm-sm d-lg-none" />
        <b-navbar-toggle
          target="nav-collapse"
          left
        ></b-navbar-toggle>

        <b-collapse
          id="nav-collapse"
          is-nav
        >
          <b-navbar-nav>
            <li>
              <br class="d-lg-none" />
              <nuxt-link
                to="/wiki"
                class="btn btn-color btn-anim devBlogLink navItem"
              >Wiki</nuxt-link>
              <a
                href="http://how-to-dev.com/essentrium"
                class="btn btn-color btn-anim devBlogLink navItem"
              >Dev Blog</a>
              <a
                class="btn btn-color btn-anim navItem"
                href="https://www.instagram.com/essentrium/"
              >
                <img src="insta.png">
              </a>
              <a
                class="btn btn-color btn-anim navItem"
                href="https://twitter.com/essentrium"
              >
                <img src="twitter.png">
              </a>
              <a
                class="btn btn-color btn-anim navItem"
                href="https://www.facebook.com/essentrium"
              >
                <img src="fb.png">
              </a>
              <a
                class="bmc-button navItem"
                target="_blank"
                href="https://www.buymeacoffee.com/3Dt0Scriv"
              >
                <img
                  src="https://www.buymeacoffee.com/assets/img/BMC-btn-logo.svg"
                  alt="Buy me a coffee"
                >
                <span style="margin-left:5px">Buy me a coffee</span>
              </a>

              <login class="loginForm loginForm-lg d-none d-lg-inline-block d-xl-inline-block" />
            </li>
          </b-navbar-nav>
        </b-collapse>
      </b-navbar>
      <br />
      <link
        href="https://fonts.googleapis.com/css?family=Lato&subset=latin,latin-ext"
        rel="stylesheet"
      >
      <nuxt-link
        to="/"
        id="home-link"
      >
        <img
          src="logo.png"
          id="logo"
          alt="essentrium.net"
        >
      </nuxt-link>
      <p class="hashtags">#essentrium #tbbg #rpg #browsergame #postpostapo</p>

      <!-- <h1>essentrium</h1> -->
      <!-- <p class="sentence">Do you think, this world failed?</p>
      <p class="sentence">You have a chance to start all again!</p>
      <br>
      <p class="sentence">Create this world better place for next generation!</p> -->
      <nuxt />
      v #{{ buildVersion }}
    </div>
    <!-- Global site tag (gtag.js) - Google Analytics -->
    <!-- <script
      async
      src="https://www.googletagmanager.com/gtag/js?id=UA-137877001-1"
    >
    </script>
    <script>
    window.dataLayer = window.dataLayer || [];

    function gtag() {
      dataLayer.push(arguments);
    }
    gtag("js", new Date());
    gtag("config", "UA-137877001-1");
    </script>-->
  </div>
</template>
<script>
import login from "~/components/login";
import Version from "~/components/version";

export default {
  components: {
    login,
    Version
  },
  computed: {
    buildVersion: function () {
      return Version.buildVersion();
    }
  }
};
</script>

<style>
html {
  font-size: 16px;
  word-spacing: 1px;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  box-sizing: border-box;
}

*,
*:before,
*:after {
  box-sizing: border-box;
  margin: 0;
}
a {
  border: 1px groove gray;
  font-variant: small-caps;
}
.navbar-nav a img {
  width: 25px;
  color: #fff;
}
#app {
  border: 1px solid transparent;
  width: 100%;
  min-height: 100vh;
  background-color: #000;
  text-align: center;
  /* background-image: url("../static/bg.png"); */
  background-size: auto 100%;
  background-repeat: no-repeat;
  background-position: center;
  /* border: 0px solid blue; */
}
#content {
  /* border: 1px solid red; */
  font-family: "Times New Roman", Times, serif;
}

.btn-color {
  background-color: transparent;
  border: 1px solid #fff;
  color: #fff;
}
.btn-color:hover {
  background-color: #575757;
  color: #fff;
}
.devBlogLink {
  font-weight: bold;
  margin-right: 5%;
}
#home-link {
border: 0px;
}
#logo {
  max-width: 70%;
  border: 0px;
  /* border: 1px solid red; */
}
.loginForm {
  flex-grow: 1;
  /* border: 1px solid green; */
  margin: 0px;
}
.loginForm-lg {
  margin-left: 5vw;
}
.bmc-button {
  line-height: 36px !important;
  height: 37px !important;
  text-decoration: none !important;
  display: inline-block !important;
  color: #000000 !important;
  background-color: #ffffff !important;
  border-radius: 3px !important;
  border: 1px solid transparent !important;
  padding: 0px 9px !important;
  font-size: 17px !important;
  letter-spacing: -0.08px !important;
  box-shadow: 0px 1px 2px rgba(190, 190, 190, 0.5) !important;
  -webkit-box-shadow: 0px 1px 2px 2px rgba(190, 190, 190, 0.5) !important;
  margin: 0 !important;
  margin-left: 5% !important;
  font-family: "Lato", sans-serif !important;
  -webkit-box-sizing: border-box !important;
  box-sizing: border-box !important;
  -o-transition: 0.3s all linear !important;
  -webkit-transition: 0.3s all linear !important;
  -moz-transition: 0.3s all linear !important;
  -ms-transition: 0.3s all linear !important;
  transition: 0.3s all linear !important;
}
.bmc-button img {
  width: 27px !important;
  margin-bottom: 1px !important;
  box-shadow: none !important;
  border: none !important;
  vertical-align: middle !important;
}
.bmc-button:hover,
.bmc-button:active,
.bmc-button:focus {
  -webkit-box-shadow: 0px 1px 2px 2px rgba(190, 190, 190, 0.5) !important;
  text-decoration: none !important;
  box-shadow: 0px 1px 2px 2px rgba(190, 190, 190, 0.5) !important;
  opacity: 0.85 !important;
  color: #000000 !important;
}
.navItem {
  display: inline-block;
  vertical-align: top;
  /* border: 1px solid red; */
}
.navbar {
  margin: 0px;
  padding: 0px;
  align-content: stretch;
  /* border: 1px solid green; */
  box-sizing: border-box;
}
.navbar-nav {
  flex-grow: 1;
}
.navbar-nav ul {
  height: 100%;
}
.navbar-nav li {
  display: inline-block;
  width: 100%;
  height: 100%;
  /* border: 1px solid red; */
}
.navbar-nav li .navItem {
  margin-bottom: 3%;
}
.navbar-collapse {
  padding: 0px;
  margin: 0px;
  align-self: flex-start;
  /* border: 1px solid red; */
}
.hashtags {
  margin-top: 1%;
  color: #fff;
}
</style>
