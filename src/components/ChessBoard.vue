<template>
  <div class="container">
    <div class="board">
      <div class="board-grid">
        <span
          :class="{black: position.color=='black', highlight: clickedPosition === position}"
          class="position"
          :id="position.location"
          v-for="position in positions"
          :key="position.location"
          @click="recordMove(position)">
        </span>
      </div>
    </div>
  </div>
</template>

<script>
// importing JSON
import boardPositions from '../assets/boardPositions'

export default {
  data() {
    return {
      positions: boardPositions,
      position: null,
      isBlack: false,
      clickedPosition: ''
    }
  },
  methods: {
    recordMove(position) {
      this.clickedPosition = position
      this.$emit('moveMade', position);
    }
  }
}
</script>

<style>
.section .container .columns {
  flex-direction: row-reverse !important;
}
.board {
  position: relative;
  width: 60vw;
  height: 60vw;
  min-width: 320px;
  min-height: 320px;
  overflow: hidden;
  border: 8px solid #312E2C;
  /* hack due to wrong colors/names */
  transform: rotate(-90deg);
}
.board-grid {
	display: grid;
	grid-template-columns: repeat(8, 12.5%);
	grid-template-rows: repeat(8, 12.5%);
  background: #FFFFFF;
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
}
.position {
  width: 100%;
  height: 100%;
}
.black {
  background-color: #312E2C;
}
.position.highlight {
  background-color:#789358;
}
</style>


