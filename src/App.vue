<template>
  <div>
    <counter-page></counter-page>
  <div>
    <h3>App Vue Counter</h3>
    {{count}}
  </div>
  <div>
    <button @click.prevent="inc({value:2})">Increment</button>
  </div>
  <div>
    <todos-list></todos-list>
  </div>
  <div>
    Todos List complete :{{doneListCount}}
  </div>
  </div>
</template>

<script>
import CounterPage from './components/CounterPage.vue'
import TodosList from './components/TodosList.vue'
import {mapState, mapGetters, mapActions, mapMutations} from 'vuex';
export default {
  name: 'App',
  computed:{
    ...mapState({
          count:state => state.count,
     }),
   ...mapGetters({
       doneListCount:'doneTodosListCount'
   }),
   
  },
  components: {
    CounterPage,
    TodosList

  },
 
  methods:{
    ...mapActions({
         increment:'increment'
    }),
    ...mapMutations({
      'inc':'increment',
    })
 
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
