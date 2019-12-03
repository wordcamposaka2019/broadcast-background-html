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
  background-color: #333333;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
</style>
