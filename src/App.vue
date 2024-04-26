<template>
  <div> 
    <div id="app">
      <div>
        <router-view/>
      </div>
    </div>

    <div id="footer">
      <div id="footer-text">
        <p>
          Built with ♥ and <a href="https://vuejs.org/">Vue.js</a>. Proudly deployed on <a href="https://vercel.com/">Vercel</a> with APIs hosted on <a href="https://www.cloudflare.com/">Cloudflare</a>.
        </p>
        <p id="footer-copyright">©2024 - {{ getYear() }} Eternal</p>
      <p>Click <a href="https://www.3tnl.xyz/">here</a> to go back to the 3tnl.xyz</p>
      </div>
    </div>
  </div> 
</template>

<script>
export default {
  name: 'app',
  methods: {
    getYear() {
      return new Date().getFullYear();
    }
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=JetBrains+Mono:ital,wght@0,100..800;1,100..800&display=swap');

:root { 
  --main-font-family: Jetbrains Mono;
  /*--monospace-font-family: sfmono-regular, consolas, liberation mono, menlo, monospace;*/
  --background-color: #000000;
  --background-image: url(./assets/noword.png);
  --text-color: #ffffff;
  --footer-color: #ffffff;
  --link-color: #050506;
  --code-color: #bd10e0;
}

html,
body {
  background-color: var(--background-color);
  background-image: var(--background-image);
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
  background-attachment: fixed;
  font-size: 18px;
  backdrop-filter: blur(10px);
  position: relative;
}

/*@media (max-width: 768px) { 
  html, body {
    background-image: none; 
  }
}*/

html::before,
body::before {
  content: "";
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.7);
  z-index: -1;
}

#app {
  font-family: var(--main-font-family), var(--monospace-font-family);
  color: var(--text-color);
  margin: 0;
  padding: 0;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  max-width: 90vw;
  margin: 0 auto;
}

.container {
  max-width: 2600px;
  margin: 0 auto;
  padding: 20px;
  border: 2px solid #fff;
  border-radius: 10px;
}

#footer {
  margin-top: auto;
  padding: 20px 20px;
  background-color: rgba(0, 0, 0, 0);
}

#footer p {
  color: var(--footer-color);
  line-height: initial;
}

#footer-text {
  margin: 0px auto;
  max-width: 664px;
  color: #ffffff;
  font-family: var(--main-font-family), var(--monospace-font-family);
}

#footer-text a,
#footer-copyright {
  color: #ffffff;
  text-decoration: underline;
}
</style>
