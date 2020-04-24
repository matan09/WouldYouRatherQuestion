<template>
    <div>
        <div>
            <div v-for="obj in questions" :key="obj.id">
                    <h2>{{ obj.question }}</h2>
                    <input type="radio" v-model="choice" v-bind:value="obj.answer1" v-on:change="$emit('answer-changed', choice)">
                    <label>{{obj.answer1}}</label>
                    <input type="radio" v-model="choice" v-bind:value="obj.answer2" v-on:change="$emit('answer-changed', choice)">
                    <label>{{obj.answer2}}</label>
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
    props: {
        questions: Array
    }
    
    
     
    
}
</script>


<style>

</style>