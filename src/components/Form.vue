<template>
    <section class="playerForm">

        <div class="instructions">
            <h1>High &#38; Low Card Game!</h1>
            <p><span>High card wins!</span></p>
            <p>Pick your best hand 4, and play the CPU.</p>
            <p>Valid cards include:</p>
            <p> 2, 3, 4, 5, 6, 7, 8, 9, 10, J, Q, K, A</p>
        </div>

        <form>
            <!--Get user name and save it in a variable.-->
            <label for="userNameInput"> Enter your name</label>
            <input 
                type="text" 
                name="userNameInput" 
                id="userNameInput" 
                v-model.lazy="formData.userName" 
                placeholder="Player name" 
                minlength="3"
                maxlength="10"
                required
            >

            <!-- Get playersHand -->
            <label for="playerHandInput"> Enter four cards</label>
            <input 
                type="text" 
                name="playerHandInput" 
                id="playerHandInput" 
                class="playerHandInput"
                placeholder="476K" 
                minlength="4"
                maxlength="4"
                required
                v-model="formData.playerInput"
            >

            <!-- on Click prevent re-loading page and trigger functions -->
            <button @click.prevent="submitForm">Play Hand</button>
        </form>
    </section>
</template>

<script>

    export default {
        data(){
            return{
                formData:{
                    userName: '',
                    playerInput:'',
                }  
            }
        },
        methods:{
            //On submit perform these functions
            submitForm(){
                // //Take user string input and split and put in to a new array
                 let cards = this.formData.playerInput.split("");

                //get bus and send cards with the val of formData.cards
                this.$emit('cards', cards)

                //get bus and send userName with the val of formData.userName
                this.$emit('userName', this.formData.userName)

                console.log("playerHand", cards)
                console.log(this.formData.userName) 
            },
        }
    }
</script>

<style scoped>
    label{
        visibility:hidden;
        position: absolute;
    }
    .playerHandInput{
        letter-spacing: 0.5rem;
    }
</style>