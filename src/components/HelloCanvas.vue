<template>
  <div class="hello-canvas">
    <h2>Hello Canvas</h2>
    <canvas id="canvas" width="1334" height="750" ref="canvas" />
  </div>
</template>

<script>
export default {
  name: 'HelloCanvas',

  methods: {
    gameLoop() {
      if(Date.now() - this.lastUpdate >= this.timePerFrame) {
        this.frameIndex++;
        if(this.frameIndex >= this.numberOfFrames) {
            this.frameIndex = 0;
        }
        this.lastUpdate = Date.now();
      }

      if (this.frameIndex > this.maxFrame) {
        this.frameIndex = 0;
      }
      this.ctx.drawImage(
        this.img,
        0,
        this.frameIndex * this.frameHeight,
        this.frameWidth,
        this.frameHeight,
        0,
        0,
        this.frameWidth,
        this.frameHeight,
      );
      
      
      window.requestAnimationFrame(this.gameLoop);
    }
  },

  mounted() {
    this.ctx = this.$refs.canvas.getContext('2d');

    this.img = new Image();
    this.img.src = 'https://dlgarenanow-a.akamaihd.net/mgames/kgtw/events/202007TelCgacha/cdn/animation/animation-arrow-light.jpg';

    this.frameWidth = 1334;
    this.frameHeight = 750;
    this.numberOfFrames = 25;
    this.frameIndex = 0;
    this.lastUpdate = 0;
    this.timePerFrame = 20;

    this.img.onload = () => {
      this.gameLoop();
    }
  }
}
</script>

<style scoped>

</style>
