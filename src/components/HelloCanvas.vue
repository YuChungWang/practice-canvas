<template>
  <div class="hello-canvas">
    <div class="machine" />
    <canvas ref="canvas" class="canvas" />
  </div>
</template>

<script>
export default {
  name: 'HelloCanvas',

  data() {
    return {
      frameWidth: 1334,
      frameHeight: 750,
      numberOfFrames: 25,
      frameIndex: 0,
      lastUpdate: 0,
      timePerFrame: 20,
    }
  },

  methods: {
    setCanvasSize() {
      this.$refs.canvas.width = this.frameWidth;
      this.$refs.canvas.height = this.frameHeight;
    },
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
    this.img = new Image();
    this.img.src = 'https://dlgarenanow-a.akamaihd.net/mgames/kgtw/events/202007TelCgacha/cdn/animation/animation-arrow-light.jpg';

    this.ctx = this.$refs.canvas.getContext('2d');
    this.setCanvasSize();

    this.img.onload = () => {
      this.gameLoop();
    }
  }
}
</script>

<style lang="scss" scoped>
.hello-canvas {
  position: relative;
  width: 1334px;
  height: 750px;

  .machine {
    position: absolute;
    bottom: 0;
    left: calc(50% - 401px);
    width: 802px;
    height: 750px;
    background: url('https://dlgarenanow-a.akamaihd.net/mgames/kgtw/events/202007TelCgacha/cdn/animation/animation-machine.png')
  }

  .canvas {
    position: absolute;
    top: 0;
    left: 0;
    mix-blend-mode: screen;
  }
}
</style>
