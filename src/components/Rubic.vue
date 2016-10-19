<template>
  <div class="container">
    <div class="rubic-container">
      <div class="rubic">
        <div
          class="piece-container"
          v-for="({ x, y, z }) in accords"
          :class="`x-${x} y-${y} z-${z}`"
          :key="`${x}-${y}-${z}`"
        >
          <cube :accordinate="accordinates[x][y][z]" :width="width"></cube>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Cube from './Cube'

export default {
  name: 'rubic',
  components: {
    Cube
  },
  props: {
    level: {
      type: Number,
      required: true
    },
    animation: {
      type: Boolean
    },
    width: {
      type: Number,
      required: true
    }
  },
  data() {
    return {
      accordinates: {}
    }
  },
  computed: {
    accords() {
      const accords = []
      for (let x = 0; x < this.level; x++) {
        for (let y = 0; y < this.level; y++) {
          for (let z = 0; z < this.level; z++) {
            accords.push({ x, y, z })
          }
        }
      }
      return accords
    }
  },
  created() {
    for (let x = 0; x < this.level; x++) {
      this.accordinates[x] = {}
      for (let y = 0; y < this.level; y++) {
        this.accordinates[x][y] = {}
        for (let z = 0; z < this.level; z++) {
          this.accordinates[x][y][z] = { x, y, z }
        }
      }
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.rubic-container {
  height: 600px;
  display: flex;
  align-items: center;
  justify-content: center;
}

.rubic {
  position: relative;
}

.piece-container {
  position: absolute;
}
</style>
