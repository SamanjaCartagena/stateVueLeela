<template>
  <div>
     <div>{{count}}</div>

  <div>
      <button @click.prevent="onIncrement()">Increment1</button>
  </div>
  </div>
</template>

<script>
export default {
   data(){
       return{
         
}
   },
   computed:{
     count(){
         return this.$store.state.count;
     }
   },
   methods:{
       onIncrement(){
           this.$store.dispatch('actionA').then((response) =>{
               console.log("calling then success")
               console.log(response)
           })
       }
   }
}
</script>

<style>

</style>