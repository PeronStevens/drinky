<template>
  <Drink />
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import Drink from './components/Drink'

export default {
  name: 'app',
  components: {
    Drink
  }
}
</script>

<style>
boay {
  background: lightgrey;
}
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
