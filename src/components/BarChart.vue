<script setup lang="ts">
import { computed } from 'vue'
const props = withDefaults(defineProps<{
  items?: { label: string; value: number }[]
  max?: number
  label?: string
}>(), {
  items: () => [
    { label: 'Lorem', value: 38 }, { label: 'Ipsum', value: 64 },
    { label: 'Dolor', value: 52 }, { label: 'Amet', value: 86 },
  ],
  max: 100,
  label: 'Lorem ipsum',
})
const upper = computed(() => Math.max(1, props.max, ...props.items.map(item => item.value)))
const step = computed(() => 284 / Math.max(1, props.items.length))
const ticks = computed(() => Array.from({ length: 5 }, (_, i) => upper.value * i / 4))
</script>
<template>
  <svg class="bar-chart" viewBox="0 0 680 350" role="img" :aria-label="label">
    <title>{{ label }}</title>
    <desc>{{ items.map(item => `${item.label}: ${item.value}`).join('; ') }}</desc>
    <g v-for="tick in ticks" :key="tick">
      <line :x1="126 + 470 * tick / upper" y1="10" :x2="126 + 470 * tick / upper" y2="295" stroke="var(--deck-border)" />
      <text :x="126 + 470 * tick / upper" y="326" text-anchor="middle" class="chart-tick">{{ Number(tick.toFixed(1)) }}</text>
    </g>
    <g v-for="(item, i) in items" :key="i">
      <text x="106" :y="10 + step * (i + .5) + 7" text-anchor="end" class="chart-label">{{ item.label }}</text>
      <rect x="126" :y="10 + step * i + step * .18" :width="470 * Math.max(0, item.value) / upper" :height="step * .64" rx="2" :fill="i === items.length - 1 ? 'var(--deck-accent)' : 'var(--deck-accent-surface)'" />
      <text :x="138 + 470 * Math.max(0, item.value) / upper" :y="10 + step * (i + .5) + 7" class="chart-label">{{ item.value }}</text>
    </g>
  </svg>
</template>
