<template>
  <div id="app">
    <div id="wrap">
      <router-view/>
    </div>
  </div>
</template>

<style>
html, body {
  padding: 0;
  margin: 0;
  background-color: #88CDE5;
}

#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #ffffff;
}

#wrap {
  width: 100vw;
  height: calc((100vw / 16) * 9);
  background-image: url('assets/wco2019_bg.png');
  background-repeat: no-repeat;
  background-size: contain;
}
</style>
