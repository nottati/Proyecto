<template class="color">
  <div id="app">
    <barra/>
    <div>    
    <pizarron/>
    </div>
  </div>
</template>

<script>
import pizarron from './components/pizarron.vue'
import barra from './components/barra.vue'

export default {
  name: 'app',
  components: {
   pizarron,
   barra
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 50px;
  margin-bottom: 0px;
  background-color: rgb(48, 226, 226);
  
  
}



</style>
