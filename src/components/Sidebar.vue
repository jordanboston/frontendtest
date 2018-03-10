<template>
  <div class="sidebar has-text-centered">
    <h3 class="has-text-weight-bold">Moves Made</h3>
    <ul v-for="move in moves" :key="move.index">
      <li class="tag has-addons">
        <span class="tag">Position</span>
        <span class="tag is-success">{{ move }}</span>
      </li>
    </ul>
    <button @click="reset" class="button">Reset</button>
  </div>
</template>

<script>
export default {
  props: {
    moves: Array
  },
  methods: {
    reset() {
      this.$emit('clearMoves')
    }
  }
}
</script>

<style scoped>
  .sidebar {
    min-height: 30vh;
    padding: 15px 10px 20px;
  }
  .tag.is-success {
    background-color: #789358;
  }
  .button {
    margin-top: 15px;
  }
</style>

