<template>
  <img alt="Vue logo" src="./assets/logo.png">

  <Counter title="Entraron" v-bind:start="101"/>
  <!-- //Este y el de abajo es lo mismo se quita el v-bind y solo se dejan los : -->
   <!-- <Counter title="Entraron" :start="10"/> -->

</template>

<script>

import Counter from './components/Counter.vue'

export default {
  name: 'App',
  components:{
    Counter
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
