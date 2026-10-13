<script setup lang="ts">
import { computed } from 'vue'
const props = withDefaults(defineProps<{
  items?: { date: string; title: string; detail: string }[]
  label?: string
}>(), {
  items: () => [
    { date: '01', title: 'Lorem ipsum', detail: 'Dolor sit amet' },
    { date: '02', title: 'Consectetur', detail: 'Adipiscing elit' },
    { date: '03', title: 'Sed eiusmod', detail: 'Tempor incididunt' },
    { date: '04', title: 'Ut labore', detail: 'Dolore magna' },
  ],
  label: 'Lorem ipsum',
})
const step = computed(() => 1128 / Math.max(1, props.items.length))
</script>
<template>
  <svg class="milestone-timeline" viewBox="0 0 1128 260" role="img" :aria-label="label">
    <title>{{ label }}</title>
    <line v-if="items.length" x1="12" y1="103" :x2="12 + step * (items.length - 1)" y2="103" stroke="var(--deck-border)" stroke-width="2" />
    <g v-for="(item, i) in items" :key="i">
      <text :x="12 + step * i" y="64" class="diagram-number">{{ item.date }}</text>
      <circle :cx="12 + step * i" cy="103" r="7" fill="var(--deck-accent)" />
      <text :x="12 + step * i" y="157" class="timeline-title">{{ item.title }}</text>
      <text :x="12 + step * i" y="193" class="diagram-detail">{{ item.detail }}</text>
    </g>
  </svg>
</template>
