<template>
  <div id="app">
    <!-- Form Component -->
    <compForm
    @userName="name = $event"
    @cards="playerCardHand = $event"
    :deck = deck
    >
    </compForm>

    <!-- Main content -->
    <main>
        <h2>{{name}}'s Hand</h2>
        <!-- loop playerCardHand and print each card to page -->
        <p v-for="(key,value,index) in playerCardHand" :key="index" >
           <span>{{key}}</span>
        </p>

        <h2>CPU's Hand</h2>
        <p v-for="(key,value,index) in cpuCardHand" :key="index" >
           <span>{{key}}</span>
        </p>
    </main>

  </div>
</template>

<script>
import compForm from "./components/Form.vue"
  export default {
    data(){
      return{
        //username
        name:"user",
        // players cards
        playerCardHand:[],
        // newPlayerHand with value 
        newPlayerHand:{},
        //userScore
        userScore: Number,
        //cpuScore
        cpuScore: Number,
        // computers cards
        cpuCardHand:{ },
        //card and value to compare when calc score
        deck:{
          "2":2,
          "3":3,
          "4":4,
          "5":5,
          "6":6,
          "7":7,
          "8":8,
          "9":9,
          "10":10,
          "j":11,
          "q":12,
          "k":13,
          "a":14
        },
      }
    },        
    //resgerstering componets
    components:{
      compForm,
    },
    methods:{

      //get cpu hand
      // setHand: function(){
      // // Get random number
      //   let rand = this.names[Math.floor(Math.random() * this.names.length)];
      //   //Run this four times
      //   for(i = 0; i < this.playerCardHand.length; i++){
      //     // push a card with value from deck with index of rand to cpuCardHand
      //     this.cpuCardHand.push(this.deck[rand])
      //  } 
      // },

      //match the sting with key in deck object and push key to newPlayerHand object
      // giveValToUserHand: function(){
      //   playerCardHand.forEach(element => {
      //       this.deck.map().match(key).push(this.newHand)
      //   });
      // }

      //get score
      //loop through both objects compare values and +1 to greater value card player


      // alertScore:function(){
      //   let userScore = this.userScore
      //   let cpuScore = this.cpuScore
      //   const winner = userScore > cpuScore ? `{{name}}` : `{{cpuScore}}`
      //   setTimeout(() => {
      //     alert(`the winner is {{winner}}`)
      //   }, 3000);
      // }
    }
  }
</script>

<style>

</style>
