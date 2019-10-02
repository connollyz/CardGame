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
                id="userNameInpu" 
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
                id="userNameInpu" 
                v-model.lazy="formData.playerHand" 
                placeholder="7 9 K 5" 
                minlength="4"
                maxlength="4"
                required
            >

            

            <!-- on Click prevent re-loading page and trigger functions -->
            <button @click.prevent="submitForm">Play</button>
        </form>
    </section>
</template>

<script>
export default {
    data(){
        return{
            formData:{
                userName: '',
                playerHand:[]
            }
        }
    },
    methods: {
        submitForm(){
            console.log('username',this.formData.userName)
            console.log('PlayerHand',this.formData.playerHand)
        }
    },
}
</script>

<style scoped>
    label{
        visibility:hidden;
    }
</style>