<script>
import Block from './components/Block.vue'
import Results from './components/Results.vue'

export default {
  name: 'App',
  components: { Block, Results, Results },
  data() {
    return {
      isPlaying: false,
      delay: null,
      score: null,
      showResults: false
    }
  },
  methods: {
    start() {
      this.delay = 2000 + Math.random() * 5000
      this.isPlaying = true
      this.showResults = false
    },
    endGame(reactionTime) {
      this.isPlaying = false
      this.showResults = true
      this.score = reactionTime
      document.getElementById('play_btn').innerText = 'Play Again'
    }
  }
}
// https://youtu.be/bc6czIBLKTg?si=psJZ8yCXRqnpkIyk&t=1406
</script>

<template>
  <h1>Ninja Vue</h1>
  <div>
    <button @click="start" id="play_btn" :disabled="isPlaying">Play</button>
  </div>
  <Block v-if="isPlaying" :delay="delay" @end="endGame"></Block>
 <Results v-if="showResults" :score="score"></Results>
</template>

<style scoped>
h1 {
  border-bottom: 1px solid #ccc;
  width: 100%;
  text-align: center;
  margin-bottom: 20px;
}

button {
  padding: 10px 20px;
  border-radius: 5px;
  border: 1px solid #ccc;
  /*button with gradient color green and silver*/
  background: rgb(78, 81, 79);
  background: linear-gradient(120deg, rgb(23, 85, 209) 0%, rgb(210, 226, 207));
  font-size: 1.2rem;
  cursor: pointer;
}

button:hover {
  background: rgb(23, 85, 209);
  color: white;
}
</style>
