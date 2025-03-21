<template>
  <div class="bg-gray-500 rounded-lg shadow-lg overflow-hidden">
    <div class="p-4">
      <h4 class="text-xl font-semibold">{{ title }}</h4>
      <p class="text-gray-600 mt-2">{{ body }}</p>
    </div>
  </div>
</template>

<script setup>
defineProps({
  title: String,
  description: String,
  body: String,
});
</script>
