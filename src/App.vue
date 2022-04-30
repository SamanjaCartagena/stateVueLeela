<template>
  <div>
    <counter-page></counter-page>
  <div>
    {{$store.state.count}}
  </div>
  </div>
</template>

<script>
import CounterPage from './components/CounterPage.vue'
export default {
  name: 'App',
  components: {
    CounterPage

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
