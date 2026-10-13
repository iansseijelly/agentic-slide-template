<script setup>
import DeckFrame from '../components/DeckFrame.vue'
</script>
<template>
  <DeckFrame>
    <div class="slide-heading"><slot /></div>
    <figure class="figure-block">
      <div class="figure-content"><slot name="figure" /></div>
      <figcaption v-if="$slots.caption"><slot name="caption" /></figcaption>
    </figure>
  </DeckFrame>
</template>
