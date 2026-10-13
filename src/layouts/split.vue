<script setup>
import DeckFrame from '../components/DeckFrame.vue'
defineProps({ ratio: { type: String, default: 'equal' } })
</script>
<template>
  <DeckFrame>
    <div class="slide-heading"><slot /></div>
    <div class="split-columns" :class="ratio">
      <div><slot name="left" /></div>
      <div><slot name="right" /></div>
    </div>
    <div v-if="$slots.bottom" class="bottom-note"><slot name="bottom" /></div>
  </DeckFrame>
</template>
