<script setup>
import { ref, onMounted } from 'vue'

defineProps({
  display: Boolean
})
</script>

<template>
  <div v-if="display" class="card">
    Categories
  </div>
</template>

<style scoped>

</style>