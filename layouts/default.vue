<template>
  <div id="app">
    <div id="content">
      <h1>essentrium</h1>
      <h3 class="hashtags">#essentrium #tbbg #rpg #browsergame #postapo</h3>
      <p class="sentence">Do you think, this world failed?</p>
      <p class="sentence">You have a chance to start all again!</p>
      <br>
      <p class="sentence">Create this world better place for next generation!</p>
      <a
        href="http://how-to-dev.com/essentrium"
        class="btn btn-dark"
      >Dev Blog</a>
      <div id="social">
        <a
          class="btn btn-dark"
          href="https://www.instagram.com/essentrium/"
        >Instagram</a>
        <a
          class="btn btn-dark"
          href="https://twitter.com/essentrium"
        >Twitter</a>
        <a
          class="btn btn-dark"
          href="https://www.facebook.com/essentrium/"
        >Facebook</a>
      </div>
      <link
        href="https://fonts.googleapis.com/css?family=Lato&subset=latin,latin-ext"
        rel="stylesheet"
      >
      <br>
      <br>
      <a
        class="bmc-button"
        target="_blank"
        href="https://www.buymeacoffee.com/3Dt0Scriv"
      >
        <img
          src="https://www.buymeacoffee.com/assets/img/BMC-btn-logo.svg"
          alt="Buy me a coffee"
        >
        <span style="margin-left:5px">Buy me a coffee</span></a>
    </div>
    <!-- Global site tag (gtag.js) - Google Analytics -->
    <script
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
    </script>

    <nuxt />
  </div>
</template>

<style>
html {
  font-family: "Source Sans Pro", -apple-system, BlinkMacSystemFont, "Segoe UI",
    Roboto, "Helvetica Neue", Arial, sans-serif;
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

.button--green {
  display: inline-block;
  border-radius: 4px;
  border: 1px solid #3b8070;
  color: #3b8070;
  text-decoration: none;
  padding: 10px 30px;
}

.button--green:hover {
  color: #fff;
  background-color: #3b8070;
}

.button--grey {
  display: inline-block;
  border-radius: 4px;
  border: 1px solid #35495e;
  color: #35495e;
  text-decoration: none;
  padding: 10px 30px;
  margin-left: 15px;
}

.button--grey:hover {
  color: #fff;
  background-color: #35495e;
}
#app {
  border: 1px solid transparent;
  width: 100vw;
  height: 100vh;
  background-color: #000;
  text-align: center;
  background-image: url("../static/bg.png");
  background-size: auto 100%;
  background-repeat: no-repeat;
  background-position: center;
}
#content {
  /* border: 1px solid red; */
  margin-top: 5vh;
  font-family: "Segoe UI", Tahoma, Geneva, Verdana, sans-serif;
}
h1 {
  color: #3b8070;
  font-size: 32pt;
}
.hashtags {
  margin-bottom: 5vh;
  background-color: rgba(1, 1, 1, 0.5);
  font-size: 8pt;
}
.sentence {
  font-size: 16pt;
}
a {
  margin: 0px 1vw;
  border: 1px groove gray;
  margin-top: 50px;
  font-variant: small-caps;
}
#social a {
  display: inline-block;
}
#social {
  margin-top: 25px;
}
.bmc-button img {
  width: 27px !important;
  margin-bottom: 1px !important;
  box-shadow: none !important;
  border: none !important;
  vertical-align: middle !important;
}
.bmc-button {
  line-height: 36px !important;
  height: 37px !important;
  text-decoration: none !important;
  display: inline-flex !important;
  color: #000000 !important;
  background-color: #ffffff !important;
  border-radius: 3px !important;
  border: 1px solid transparent !important;
  padding: 0px 9px !important;
  font-size: 17px !important;
  letter-spacing: -0.08px !important;
  box-shadow: 0px 1px 2px rgba(190, 190, 190, 0.5) !important;
  -webkit-box-shadow: 0px 1px 2px 2px rgba(190, 190, 190, 0.5) !important;
  margin: 0 auto !important;
  font-family: "Lato", sans-serif !important;
  -webkit-box-sizing: border-box !important;
  box-sizing: border-box !important;
  -o-transition: 0.3s all linear !important;
  -webkit-transition: 0.3s all linear !important;
  -moz-transition: 0.3s all linear !important;
  -ms-transition: 0.3s all linear !important;
  transition: 0.3s all linear !important;
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
</style>