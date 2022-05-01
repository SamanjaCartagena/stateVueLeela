<template>
  <div>
    <counter-page></counter-page>
  <div>
    <h3>App Vue Counter</h3>
    {{count}}
  </div>
  <div>
    <button @click.prevent="onIncrement">Increment</button>
  </div>
  </div>
</template>

<script>
import CounterPage from './components/CounterPage.vue'
export default {
  name: 'App',
  computed:{
   count(){
     return this.$store.state.count
   }
  },
  components: {
    CounterPage

  },
  methods:{
    onIncrement(){
      this.$store.commit(
        {type:'increment',value:3});
    }
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
