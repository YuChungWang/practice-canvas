<template>
  <div id="app">
    <img src="./assets/icon-canvas.jpg" class="icon">
    <p>Hello Canvas</p>
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
  margin-top: 50px;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;

  .icon {
    width: 60px;
    height: 60px;
    margin: 16px 0 0;
  }

  p {
    margin: 6px;
    font-size: 20px;
    font-weight: bold;
  }
}
</style>
