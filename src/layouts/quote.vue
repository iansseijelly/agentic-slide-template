<script setup>
import DeckFrame from '../components/DeckFrame.vue'
defineProps({ quoteFont: { type: String, default: 'inter' } })
</script>
<template>
  <DeckFrame variant="quotation">
    <div v-if="$slots.label" class="eyebrow"><slot name="label" /></div>
    <blockquote :class="{ 'quote-courier': quoteFont === 'courier' }"><slot /></blockquote>
    <div v-if="$slots.attribution" class="quote-attribution"><slot name="attribution" /></div>
  </DeckFrame>
</template>
