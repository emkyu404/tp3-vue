<template>
  <base-header />
  <HomePage></HomePage>
  <base-footer />
</template>

<script>
import HomePage from './components/HomePage.vue'
import BaseHeader from './components/BaseHeader.vue'

export default {
  name: 'App',
  components: {
    HomePage,
    BaseHeader
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
}
</style>
