<template>

 <h1>Reaction Timer</h1>
 <button @click="start" class="btn btn-success mt-2" :disabled="playing">Play</button>
 <Block v-if="playing" :delay="delay" @end="endGame"/>

 <Results v-if="showResult"  :score="score" />

</template>

<script>
import Block from './components/Block.vue'
import Results from './components/Results.vue'

export default {
  name: 'App',
  components: {Block,Results},
  data() {
    return {
      time: 0,
      delay: null,
      playing: false,
      score: 0,
      showResult: false
    }
  },
  methods: {
    start() {
      this.delay = 2000 + Math.random() * 5000;
      this.playing = true;
      this.showResult = false;
    },
    endGame(reactionTime){
      this.score = reactionTime;
      this.playing = false;
      this.showResult = true;
    }
  }

}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
