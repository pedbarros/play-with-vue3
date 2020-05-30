<template>
  <div class="modal">
    <slot></slot>
    <button @click="$emit('close')">Dismiss</button>
  </div>
</template>

<style scoped>
::v-slotted(p) {
  font-style: italic;
}
</style>