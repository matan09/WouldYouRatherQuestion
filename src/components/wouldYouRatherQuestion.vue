<template>
    <div>
        <div>
            <div v-for="{id, question, answer1, answer2} in questions" :key="id">
                    <h2>{{ question }}</h2>
                    <input type="radio" v-model="choice" v-bind:value="answer1" v-on:change="$emit('answer-changed', choice)">
                    <label>{{answer1}}</label>
                    <input type="radio" v-model="choice" v-bind:value="answer2" v-on:change="$emit('answer-changed', choice)">
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
        question: questions.question,
        answer1: questions.answer1,
        answer2: questions.answer2
            
        }
    },
    props: {
        questions: Array
    }
    
    
     
    
}
</script>


<style>

</style>