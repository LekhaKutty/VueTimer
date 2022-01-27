<template>
  <h1>Reaction Timmer</h1>
  <button @click="startPlay" :disabled="isPlaying">Play</button>
  <Block v-if="isPlaying" :delay="delay" @endingGame="endGame"/>
  <p v-if="showResults">Reaction Time: {{score}}</p>
</template>

<script>
import Block from './components/Block.vue'
export default {
  name: 'App',
  components: {
    Block
  },
  data() {
    return{
      isPlaying: false,
      delay: null,
      score: null,
      showResults: false
    }
  },
  methods: {
    startPlay() {
      this.showResults = false
      this.delay = 2000 + Math.random() * 5000
      this.isPlaying = true
     
    },
    endGame (reactionTimeFromBlock) {
      this.score = reactionTimeFromBlock
      this.isPlaying = false
      this.showResults = true
      console.log(this.score)
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
  color: #444;
  margin-top: 60px;
}
</style>
