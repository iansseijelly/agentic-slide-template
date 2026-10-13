<script setup>
defineProps({ label: { type: String, default: 'Lorem ipsum' } })
</script>
<template>
  <svg class="figure-placeholder" viewBox="0 0 1128 320" role="img" :aria-label="label">
    <rect width="1128" height="320" rx="4" fill="var(--deck-surface)" />
    <circle cx="825" cy="86" r="32" fill="var(--deck-accent-surface)" />
    <path d="M 630 265 L 765 133 L 838 204 L 909 139 L 1044 265 Z" fill="var(--deck-border)" />
    <path d="M 630 265 L 765 133 L 838 204 L 774 265 Z" fill="var(--deck-accent-surface)" />
    <text x="48" y="161" style="font-size: 34px" fill="var(--deck-text)">{{ label }}</text>
    <text x="48" y="202" style="font-size: 20px" fill="var(--deck-muted)">16 : 9 · 4 : 3 · 1 : 1</text>
  </svg>
</template>
