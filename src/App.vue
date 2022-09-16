<template>
  <router-view/>
</template>

<style lang="scss">
@import '/global/index';
html {
  scroll-behavior: smooth;
  overflow-x: hidden;
}
body {
  font-family: 'MONO';
  margin: 0;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #fff;
  background-color: #1A1A1A;
}

nav {
  padding: 30px;

  a {
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: #42b983;
    }
  }
}
</style>
