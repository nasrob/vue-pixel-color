<template>
  <ColorPicker :color=color />
  <Canvas :pixels=pixels />
</template>

<script>
import Canvas from './components/Canvas'
import ColorPicker from './components/ColorPicker'

const defaultColor = 'white'

export default {
  name: 'App',
  components: {
    Canvas,
    ColorPicker
  },
  data: function () {
    return {
      color: defaultColor,
      pixels: Array(30 * 30).fill().map(() => defaultColor)
    }
  },
  mounted() {
    this.eventBus.on('updatecolor', color => {
      this.color = color
    })

    this.eventBus.on('clickedpixel', index => {
      this.pixels.splice(index, 1, this.color)
    })
  }
}
</script>

<style>
#app {
  background-color: #333;
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
}
</style>
