<template>
  <div id="app">
    <Container/>
  </div>
</template>

<script>
import Container from './components/Container.vue'

export default {
  name: 'App',
  title: 'George Jennison Portfolio',
  components: {
    Container
  },

  created() {
    document.title = "George Jennison Portfolio";
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
}
html{
  background-color: rgba(200,225,255,0.2)
}
</style>
