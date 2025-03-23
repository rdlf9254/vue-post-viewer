<template>
  <div class="p-4">
    <div
      v-if="!data || data.length === 0"
      class="flex flex-col items-center justify-center py-6 text-gray-600 dark:text-gray-300"
    >
      <i class="uil uil-database-slash text-5xl text-gray-400"></i>
      <p class="mt-2 text-lg font-semibold">Nenhum dado disponível</p>
      <p class="text-sm text-gray-500">Tente novamente mais tarde.</p>
    </div>
    <div
      v-else
      class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-4 gap-4 p-4"
    >
      <card
        v-for="(item, i) in data"
        :key="i"
        :title="item.title"
        :body="item.body"
        class="w-full h-full"
      />
    </div>
  </div>
</template>

<script setup>
import Card from "@components/Card.vue";

defineProps({
  data: Array,
});
</script>
