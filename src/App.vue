<template>

 <h1>Reaction Timer</h1>
 <button @click="start" class="btn btn-primary mt-2" :disabled="playing">Play</button>

 <Block v-if="playing" :delay="delay"/>

</template>

<script>
import Block from './components/Block.vue'

export default {
  name: 'App',
  components: {Block},
  data() {
    return {
      time: 0,
      delay: null,
      playing: false,
      score: 0,
      highScore: 0
    }
  },
  methods: {
    start() {
      this.delay = 2000 + Math.random() * 5000;
      this.playing = true;
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
