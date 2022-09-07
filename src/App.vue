<template>
  <div id="app">
    <SliderVue/>
  </div>
</template>

<script>
import SliderVue from './components/SliderVue.vue'

export default {
  name: 'App',
  components: {
    SliderVue
  }
}
</script>

<style>
#app {
  overflow: hidden;
  font-family: Kinopoisk, Futura, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
</style>
