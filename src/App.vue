<template>
  <div>
    <Header />
    <section class="section">
      <div class="container">
        <div class="columns">
          <div class="column is-three-quarters">
            <chess-board />
          </div>
            <div class="column">
            <sidebar />
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<script>
import Header from './components/Header'
import Sidebar from './components/Sidebar'
import ChessBoard from './components/ChessBoard'

export default {
  components: {
    Header,
    ChessBoard,
    Sidebar
  }
}
</script>

<style src="bulma"></style>
