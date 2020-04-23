<template>
  <div id="app">
    <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
    <h1>Would Your Rather?</h1>
    <wouldYouRatherQuestion 
    v-bind:questions="questions"
    
    v-on:answer-changed="userAnswers" 
    ></wouldYouRatherQuestion>
    <div> 
      <h1>{{ selectionHeader }}</h1>
    </div>

    <div> 
    <p class="user-answers">
      <span>...? Try making a selection above</span>
      <ul>
        <li v-for="choice in userChoices" :key="choice"><span>{{choice}}</span></li>
      </ul>
    </p>
    </div>
  </div>
</template>

<script>
import wouldYouRatherQuestion from './components/wouldYouRatherQuestion.vue'

export default {
  name: 'App',
  components: {
    wouldYouRatherQuestion
  },
   data() {
        return{
          selectionHeader: 'You Would Rather...',
          userSelectionMessage: [],
          userChoices: [],
            questions: [
        {
            id:0,
            question :'would you want to be a writer or famous?',
            answer1: 'writer',
            answer2: 'famous'
        },
        {
            id:1,
            question :'Would you rather live in a house shaped like a circle or a house shaped like a triangle?',
            answer1: 'Circle',
            answer2: 'Triangle'
        },
        {
            id:2,
            question :'Would you rather be a super hero or wizard?',
            answer1: 'hero',
            answer2: 'Wizard'
        }
        ],   
     }
                
    },
    methods: {
      userAnswers(choice){
        console.log('msg is emitted')
        this.userChoices.push(choice)
      }
    }
}
</script>

<style>


</style>
