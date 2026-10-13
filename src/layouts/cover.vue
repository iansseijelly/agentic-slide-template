<script setup>
import DeckFrame from '../components/DeckFrame.vue'
</script>
<template>
  <DeckFrame variant="cover">
    <div class="cover-main"><slot /></div>
    <div v-if="$slots.bottom" class="cover-bottom"><slot name="bottom" /></div>
  </DeckFrame>
</template>
