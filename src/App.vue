<template>

  <div id="app">
    <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
    <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
    <Game/>
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import Game from './components/Game.vue'

export default {
  name: 'App',
  components: {
   // HelloWorld
    Game
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  margin-top: 60px;
  padding: 3em;
}

body{
  background-image: url(./assets/1.png);
  background-repeat: no-repeat;
  
}
</style>
