
<template>
  <h1>Simons Reaction Timer</h1>
  <Startbutton @start-timer="startTimer" :delay="timer" :gameon="gameOn" />
  <Popupbox v-if="gameOn" :delay="timer" @stop="displayResults" />
  <Results v-if="viewResults" :result="score" />
</template>

<script>
import Popupbox from './components/Popupbox.vue';
import Startbutton from './components/Startbutton.vue';
import Results from './components/Results.vue'

export default {
  name: "App",
  components: { Popupbox, Startbutton, Results },
  data() {
    return {
      gameOn: false,
      timer: null,
      score: 0,
      viewResults: false,
      resultMsg: ''
    }
  },
  methods: {
    startTimer() {
      console.log('Appearance timer started!')
      this.viewResults = false
      this.gameOn = !this.gameOn
      this.showResults = false
      this.timer = 1000 + Math.random() * 4000
    },
    displayResults(reactiontime) {
      console.log('The results are in!', reactiontime)
      this.score = reactiontime
      this.viewResults = true
      this.gameOn = !this.gameOn
    }
  }
}
</script>

<style>
#app {
  background-color: lightgrey;
  width: 100vw;
  height: 100vh;
  /* text-align: center; */
  color: rgb(63, 61, 61);
  font-weight: 800;
  padding-top: 100px;
  display: flex;
  flex-direction: column;
  align-items: center;
}
</style>
