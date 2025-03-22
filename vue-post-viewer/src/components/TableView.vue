<template>
  <div class="overflow-x-auto p-4">
    <div
      v-if="!data || data.length === 0"
      class="flex flex-col items-center justify-center py-6 text-gray-600 dark:text-gray-300"
    >
      <i class="uil uil-database-slash text-5xl text-gray-400"></i>
      <p class="mt-2 text-lg font-semibold">Nenhum dado disponível</p>
      <p class="text-sm text-gray-500">Tente novamente mais tarde.</p>
    </div>

    <table
      v-else
      class="min-w-full border border-gray-300 shadow-md rounded-lg overflow-hidden"
    >
      <thead class="bg-gray-800 text-white">
        <tr>
          <th class="pl-8 pr-4 py-3 text-left">Id</th>
          <th class="px-4 py-3 text-left">Detalhes</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="(item, i) in data" :key="i" class="border-b border-gray-600 bg-gray-700">
          <td class="pl-8 pr-4 py-3">
            <div class="flex flex-col">
              <div class="flex flex-row">
                <p class="text-white font-bold text-sm text-nowrap">
                  {{ item.id }}
                </p>
              </div>
            </div>
          </td>
          <td class="pr-8 pl-4 py-3">
            <div class="flex flex-col">
              <p class="text-white font-bold first-letter:uppercase">{{ item.title }}</p>
              <p class="text-gray-300 text-sm mt-1 first-letter:uppercase">{{ item.body }}</p>
            </div>
          </td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script setup>
import { defineProps } from "vue";

defineProps({
  data: Array,
});
</script>
