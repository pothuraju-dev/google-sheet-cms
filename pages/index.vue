<template>
  <h1 class="text-3xl text-center pt-8">Data from Google Sheets</h1>
  <div v-for="(card, index) in sheetResonse?.data" :key="index" class="p-4">
    {{ card }}
    <Card :card="card" />
  </div>
</template>
<script setup lang="ts">
const runtimeConfig = useRuntimeConfig()
const { data: sheetResonse } = await useFetch<{
  data: { data: { Title: string; Content: string } };
}>(
  `https://script.google.com/macros/s/${runtimeConfig.public.googleSheetId}/exec`,
  {
    headers: {}
  }
);
</script>
