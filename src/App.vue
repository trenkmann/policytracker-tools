<template>
  <div id="app">
    <CountryFinder />
  </div>
</template>

<script>
import CountryFinder from './components/CountryFinder.vue';

export default {
  name: 'app',
  components: {
    CountryFinder,
  },
};
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
