<template>
  <div
    class="p-4 bg-white rounded-lg shadow-xl place-content-center text-slate-800"
  >
    <p class="text-lg font-bold mb-2">{{ card.Title }}</p>
    <p class="text-sm">{{ card.Content }}</p>
  </div>
</template>

<script setup lang="ts">
defineProps<{ card: { Title: string; Content: string } }>();
</script>
