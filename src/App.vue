<script>
import Block from './components/Block.vue'
export default{
  name: 'App',
  components: { Block},
  data(){
    return{
      isPlaying: false,
      delay: null
    }
  },
  methods: {
    start(){
      this.delay = 2000 + Math.random() * 5000
      this.isPlaying = true

    }
}
}
// https://youtu.be/bc6czIBLKTg?si=psJZ8yCXRqnpkIyk&t=1406
</script>

<template>
  <h1>Ninja Vue</h1>
  <div>
    <button @click="start" :disabled="isPlaying">Play</button>
  </div>
  <Block v-if="isPlaying" :delay="delay"></Block>

</template>

<style scoped>

</style>
