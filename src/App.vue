<template>
  <div id="app">
    <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
    <h1>Would Your Rather?</h1>
    <wouldYouRatherQuestion
    v-for="ques in questions" v-bind:key="ques" v-bind:class="'ques-'+ques.id"
    v-bind:question="ques.question"
    v-bind:answer1="ques.answer1"
    v-bind:answer2="ques.answer2"
    
 
    
    v-on:answer-changed="userAnswers" 
    ></wouldYouRatherQuestion>
    <div> 
      <h1>{{  ResultHeader }}</h1>
    </div>

    <div> 
    <p class="userAnswers">
     
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
          ResultHeader: 'You Would Rather...',
          userChoices: [],
            questions: [
        {
            id:0,
            question :'would you Rather to be a writer or famous?',
            answer1: 'Would be a Writer',
            answer2: 'Would be  Famous'
        },
        {
            id:1,
            question :'Would you rather live in a house shaped like a circle or a house shaped like a triangle?',
            answer1: 'Live in Circle',
            answer2: 'Live in Triangle'
        },
        {
            id:2,
            question :'Would you rather be a super hero or wizard?',
            answer1: 'Super hero',
            answer2: 'Be Wizard'
        }
        ],   
     }
                
    },
    methods: {
      userAnswers(choice){
        this.userChoices.push(choice)
      }
    }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  
  color: #2c3e50;
  margin-top: 30px;
  padding:30px;
}
ul{
  text-decoration: black;
  border:1px thin gray;
  text-align: center;
  
  position: centre;
}
h1{
  text-align: center;
}

.ques-0{
  background: lightseagreen
}

.ques-1{
  background: crimson;
}

.ques-2{
  background: lightpink;
}

</style>
