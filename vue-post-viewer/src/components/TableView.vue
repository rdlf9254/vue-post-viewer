<!-- <thead>
  <tr>
    <th>index</th>
    <th>userId</th>
    <th>id</th>
    <th>title</th>
    <th>body</th>
  </tr>
</thead> -->

<!-- <tbody>
  <tr v-for="item,i in data">
    <td>{{ i }}</td>
    <td v-for="dt in item">{{ dt }}</td>
  </tr>
</tbody> -->
<template>
  <div class="overflow-x-auto p-4">
    <table
      class="min-w-full border border-gray-300 shadow-md rounded-lg overflow-hidden"
    >
      <thead class="bg-gray-800 text-white">
        <tr>
          <th class="px-4 py-2 text-left">Usuário & Post</th>
          <th class="px-4 py-2 text-left">Detalhes</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="(item, i) in data" :key="i" class="border-b border-gray-300">
          <td class="px-4 py-3">
            <div class="flex flex-col">
              <div class="flex flex-row">
                <i class="uil uil-user pr-1 text-sm"></i>
                <p class="text-gray-700 font-semibold text-nowrap">
                  Id do usuário: {{ item.userId }}
                </p>
              </div>
              <div class="flex flex-row">
                <i class="uil uil-pen pr-1 text-sm"></i>
                <p class="text-gray-500 text-sm text-nowrap">
                  Id do post: {{ item.id }}
                </p>
              </div>
            </div>
          </td>
          <td class="px-4 py-3">
            <div class="flex flex-col">
              <p class="text-gray-800 font-bold">{{ item.title }}</p>
              <p class="text-gray-600 text-sm mt-1">{{ item.body }}</p>
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
  loading: Boolean,
});
</script>
