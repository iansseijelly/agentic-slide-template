<script setup lang="ts">
import { useNav } from '@slidev/client'
const { currentPage, total } = useNav()
defineProps<{ variant?: string }>()
</script>

<template>
  <div class="slidev-layout deck" :class="variant" :data-slide-count="total" :data-slide-number="currentPage">
    <main class="deck-content"><slot /></main>
    <footer class="slide-footer">
      <span>{{ String(currentPage).padStart(2, '0') }} / {{ String(total).padStart(2, '0') }}</span>
    </footer>
  </div>
</template>
