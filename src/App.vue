<template>
  <div id="app">
    <component :is="compToRender"></component>
  </div>
</template>

<script>
import compForm from "./components/Form.vue"
import compGame from "./components/Game.vue"
import compResults from "./components/Results.vue"
  export default {
    data(){
      return{
               compToRender: "compForm"
           }
    },
    //resgerstering componets
    components:{
      compForm,
      compGame,
      compResults
    }
  }
</script>

<style>

</style>
