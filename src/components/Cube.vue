<template>
  <div class="cube" :style="style">
    <div class="face face-left"></div>
    <div class="face face-right"></div>
    <div class="face face-up"></div>
    <div class="face face-down"></div>
    <div class="face face-front"></div>
    <div class="face face-back"></div>
  </div>
</template>

<script>
export default {
  name: 'cube',
  props: {
    width: {
      type: Number,
      required: true
    },
    accordinate: {
      type: Object,
      required: true
    }
  },
  data() {
    return {
      a: 1
    }
  },
  computed: {
    style() {
      return {
        width: `${this.width}px`,
        height: `${this.width}px`
      }
    }
  }
}
</script>

<style scoped>
.cube {
  display: flex;
  align-items: center;
  justify-content: center;
  transform-style: preserve-3d;
}

.face {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  border: 6px solid #ccc;
  border-radius: 8px;
  transform-style: preserve-3d;
}

</style>