<script setup lang="ts">
import { computed, useId } from 'vue'
const props = withDefaults(defineProps<{
  steps?: { title: string; detail: string }[]
  label?: string
}>(), {
  steps: () => [
    { title: 'Lorem', detail: 'Dolor sit amet' },
    { title: 'Ipsum', detail: 'Consectetur elit' },
    { title: 'Dolor', detail: 'Sed do eiusmod' },
  ],
  label: 'Lorem ipsum',
})
const markerId = `arrow-${useId().replace(/:/g, '')}`
const step = computed(() => 1100 / Math.max(1, props.steps.length))
</script>
<template>
  <svg class="process-diagram" viewBox="0 0 1128 230" role="img" :aria-label="label">
    <title>{{ label }}</title>
    <defs><marker :id="markerId" viewBox="0 0 10 10" refX="9" refY="5" markerWidth="7" markerHeight="7" orient="auto"><path d="M 0 0 L 10 5 L 0 10 z" fill="var(--deck-accent)" /></marker></defs>
    <g v-for="(item, i) in steps" :key="i">
      <rect :x="14 + step * i" y="40" :width="step - 54" height="145" rx="3" fill="var(--deck-surface)" />
      <text :x="38 + step * i" y="75" class="diagram-number">{{ String(i + 1).padStart(2, '0') }}</text>
      <text :x="38 + step * i" y="116" class="diagram-title">{{ item.title }}</text>
      <text :x="38 + step * i" y="151" class="diagram-detail">{{ item.detail }}</text>
      <line v-if="i < steps.length - 1" :x1="step * (i + 1) - 28" y1="112" :x2="step * (i + 1) + 2" y2="112" stroke="var(--deck-accent)" stroke-width="2" :marker-end="`url(#${markerId})`" />
    </g>
  </svg>
</template>
