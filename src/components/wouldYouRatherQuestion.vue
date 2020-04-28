<template>
    <div>
        <div>
            <div>
                    <h2>{{ question }}</h2>
                    <input type="radio" v-model="choice" v-bind:value="answer1+ ','+id" v-on:change="$emit('answer-changed', choice)">
                    <label>{{answer1}}</label>
                    <input type="radio" v-model="choice" v-bind:value="answer2+ ','+id" v-on:change="$emit('answer-changed', choice)">
                    <label>{{answer2}}</label>
                </div>
        </div>
    </div>
</template>

<script>
export default {// provide what ever is in the script to what ever imports this component
    name: "wouldYouRatherQuestion",
    data(){
        return{
            choice: '',// a list of user answers
              
        }
    },
    props: {// data sent from the parent
        id: Number,
        question: String,
        answer1: String,
        answer2: String
    }
    
    
     
    
}
</script>


<style>

</style>