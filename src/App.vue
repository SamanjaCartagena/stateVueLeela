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
export default {
  name: 'App',
  computed:{
   count(){
     return this.$store.state.count
   },
   doneListCount(){
      return this.$store.getters.doneTodosListCount;
    }
  },
  components: {
    CounterPage,
    TodosList

  },
 
  methods:{
    onIncrement(){
      this.$store.commit(
        {type:'increment',value:3});
    },
    getDoneListCount(){
      return this.$store.state.todos.filter((todo)=> todo.done).length;
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
