<template>
  <base-layout>
  <home-page />
  </base-layout>
</template>

<script>
import HomePage from './components/HomePage.vue'
import BaseLayout from './components/BaseLayout.vue'

export default {
  name: 'App',
  components: {
    HomePage,
    BaseLayout
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
  display : flex;
  flex-direction : column;
  margin : none;
}

body{
  margin : 0;
}
</style>
