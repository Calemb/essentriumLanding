<template>
  <div id="app">
    <div id="content">
      <h1>essentrium</h1>
      <h3 class="hashtags">#essentrium #tbbg #rpg #browsergame #postapo</h3>
      <p class="sentence">Do you think, this world failed?</p>
      <p class="sentence">You have a chance to start all again!</p>
      <p class="sentence">Maybe the only goal is to server others? </p>
      <p class="sentence">Serve next generation so they are not bothered with our problems?</p>
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
    </div>
    <!-- Global site tag (gtag.js) - Google Analytics -->
    <script
      async
      src="https://www.googletagmanager.com/gtag/js?id=UA-137877001-1"
    ></script>
    <script>
    window.dataLayer = window.dataLayer || [];

    function gtag() {
      dataLayer.push(arguments);
    }
    gtag("js", new Date());
    gtag("config", "UA-137877001-1");
    </script>

    <!-- <nuxt /> -->
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
</style>