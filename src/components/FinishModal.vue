<template>
  <div class="modal-card" style="width: 350px">
    <header class="modal-card-head has-background-danger">
      <p class="modal-card-title has-text-light">You got them all!!</p>
    </header>
    <section class="modal-card-body">
      <Pokeball />
      <h3>Pokémon - Memory Game</h3>
      <hr />

      <div class="control">
        <div class="tags has-addons are-large">
          <span class="tag is-black">Level</span>
          <span class="tag is-warning">{{ levelCount }}</span>
        </div>

        <div class="tags has-addons are-large">
          <span class="tag is-black">Score</span>
          <span class="tag is-link">{{ score | number }}</span>
        </div>

        <div class="tags has-addons are-large">
          <span class="tag is-black">Time</span>
          <span class="tag is-info">{{ timer | secToTimeStr(false) }}</span>
        </div>
      </div>
    </section>
  </div>
</template>

<script>
import Pokeball from './Pokeball.vue'
import { mapState, mapGetters } from 'vuex'

export default {
  name: 'FinishModal',
  components: { Pokeball },
  computed: {
    ...mapGetters(['levelCount']),
    ...mapState(['score', 'level', 'timer'])
  }
}
</script>

<style scoped>
  .modal-card-title, h3 {
    text-align: center;
    font-family: monospace;
    font-weight: bold;
  }
  h3 {
    font-size: 1.5rem;
  }
</style>