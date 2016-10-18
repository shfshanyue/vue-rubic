<template>
  <div id="app">
    <rubic :level="3" :width="120"></rubic>
  </div>
</template>

<script>
import Rubic from './components/Rubic'

export default {
  name: 'app',
  components: {
    Rubic
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
}
</style>
