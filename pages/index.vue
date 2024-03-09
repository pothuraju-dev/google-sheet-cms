<template>
  <h1 class="text-3xl text-center pt-8">Data from Google Sheets</h1>
  <div v-for="(card, index) in sheetResonse?.data" :key="index" class="p-4">
    <Card :card="card" />
  </div>
</template>
<script setup lang="ts">
const { data: sheetResonse } = await useFetch<{
  data: { data: { Title: string; Content: string } };
}>(
  "https://script.google.com/macros/s/AKfycbw1BSuTvrLyIMHykdV8uH1WCzyCvEJMsQZgSSs0oi51ys863jn1u8ZEhF0IuGwJIsS0HA/exec",
  {
    headers: {}
  }
);
</script>
