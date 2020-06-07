<template>
  <div id="app">
    <Spongebob />
  </div>
</template>

<script>
import Spongebob from './components/Spongebob.vue'

export default {
  name: 'app',
  components: {
    Spongebob
  }
}
</script>

<style>
body, html {
    height: 100%;
    width: 100%;
    overflow:hidden;
}
#app {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
}
</style>
