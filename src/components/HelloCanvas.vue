<template>
  <div class="hello-canvas">
    <h1>Hello Canvas</h1>
    <canvas id="canvas" width="600" height="400" ref="canvas" />
  </div>
</template>

<script>
export default {
  name: 'HelloCanvas',

  mounted() {
    const ctx = this.$refs.canvas.getContext('2d');
    ctx.fillStyle = "rgb(200,0,0)";
    ctx.fillRect (10, 10, 55, 50);

    ctx.fillStyle = "rgba(0, 0, 200, 0.5)";
    ctx.fillRect (30, 30, 55, 50);
  }
}
</script>

<style scoped>

</style>
