<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
    <Longitud/>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import Longitud from ' .components/Longitud.vue'

export default {
  name: 'App',
  components: {
    HelloWorld
     Longitud
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
