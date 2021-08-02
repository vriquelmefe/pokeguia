<template>
  <div id="app">
    <PokeInfo />
  </div>
</template>

<script>
import PokeInfo from './components/PokeInfo.vue';


export default {
  name: "App",
  components: { PokeInfo }, 
};
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #02367a;
  margin-top: 60px;
}
</style>
