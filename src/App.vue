<template>
  <section class="section">
    <div class="container">
      <div class="columns">
        <div class="column is-three-quarters">
          <chess-board @moveMade="logMove($event)" />
        </div>
          <div class="column">
          <sidebar :moves="moveHistory" @clearMoves="resetMoves" />
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import Sidebar from './components/Sidebar'
import ChessBoard from './components/ChessBoard'

export default {
  components: {
    ChessBoard,
    Sidebar
  },
  data() {
    return {
      moveHistory: []
    }
  },
  methods: {
    logMove(position) {
      this.moveHistory.push(position.location)
      // console.table(this.moveHistory)
    },
    resetMoves() {
      this.moveHistory = []
    }
  }
}
</script>

<style src="bulma"></style>
