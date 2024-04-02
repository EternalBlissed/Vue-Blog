<template>
  <div id="app">
    <div>
      <router-view/>
    </div>
  </div>
</template>
<style>
@import url('https://fonts.googleapis.com/css2?family=JetBrains+Mono:ital,wght@0,100..800;1,100..800&display=swap');

:root { 
  --main-font-family: Jetbrains Mono;
  --monospace-font-family: sfmono-regular, consolas, liberation mono, menlo, monospace;
  --background-color: #000000;
  --background-image: url(./assets/graphite.jpg);
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
  
  /* Add blur filter */
  backdrop-filter: blur(10px); /* Adjust the blur radius as needed */
  
  /* Add overlay to darken the background */
  position: relative;
}

html::before,
body::before {
  content: "";
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.7); /* Adjust the opacity (last value) to control the darkness */
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
  background-color: rgba(0, 0, 0, 0.5);
}

</style>
