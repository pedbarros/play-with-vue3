<template>
  <button @click="toggleModalState">Open modal</button>
  <teleport to="#modal-wrapper">
    <modal v-if="modalOpen" @close="toggleModalState">
      <p>Hello, I'm a modal window.</p>
    </modal>
  </teleport>
</template>

<script>
import Modal from "./Modal.vue";
import { ref } from 'vue'

export default {
  emits: [ "close" ],
  setup () {
    const modalOpen = ref(false)

    const toggleModalState = () => {
      modalOpen.value = !modalOpen.value
    }

    return {
      modalOpen,
      toggleModalState
    }
  },
  components: {
    Modal
  }
}
</script>

<style scoped>
img {
  width: 200px;
}
h1 {
  font-family: Arial, Helvetica, sans-serif;
}
</style>
