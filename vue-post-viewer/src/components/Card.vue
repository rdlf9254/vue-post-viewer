<template>
  <div class="bg-gray-800 px-6 py-8 rounded-lg ring shadow-xl ring-gray-900/5 overflow-hidden">
    <div class="p-4">
      <h4 class="text-xl font-semibold first-letter:uppercase">{{ title }}</h4>
      <p class="text-gray-600 mt-2 first-letter:uppercase">{{ body }}</p>
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
