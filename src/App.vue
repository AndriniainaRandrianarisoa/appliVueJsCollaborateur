<template>
  <div id="app">
    <h1>Vos collaborateurs</h1>
    <Home/>
    <Liste/>
    
  </div>
</template>

<script>
import Home from './components/Home.vue'
import Liste from './components/Liste.vue'


export default {
  name: 'App',
  components: {
    Home, Liste
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
