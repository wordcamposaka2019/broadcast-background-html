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
  background-color: #65B0D4;
}

#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#wrap {
  width: 100vw;
  height: calc((100vw / 16) * 9);
  background-image: url('assets/wco2019_bg.png');
  background-repeat: no-repeat;
  background-size: contain;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
</style>
