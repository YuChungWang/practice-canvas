<template>
  <div id="app">
    <img src="./assets/icon-canvas.jpg" class="icon">
    <hello-canvas />
  </div>
</template>

<script>
import HelloCanvas from './components/HelloCanvas.vue'

export default {
  name: 'App',
  components: {
    HelloCanvas
  }
}
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.icon {
  width: 60px;
  height: 60px;
}
</style>
