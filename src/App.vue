
<template>
  <h1>Simons Reaction Timer</h1>
  <Startbutton @start-timer="startTimer" :delay="timer" :gameon="gameOn" />
  <Popupbox v-if="gameOn" :delay="timer" />
</template>

<script>
import Popupbox from './components/Popupbox.vue';
import Startbutton from './components/Startbutton.vue';

export default {
  name: "App",
  components: { Popupbox, Startbutton },
  data() {
    return {
      gameOn: false,
      timer: null,
    }
  },
  methods: {
    startTimer() {
      console.log('Appearance timer started!')
      this.gameOn = !this.gameOn
      this.timer = 1000 + Math.random() * 4000
      console.log(this.timer)
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
