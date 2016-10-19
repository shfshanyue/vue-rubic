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
* {
  box-sizing: border-box;
}

#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
}
</style>
