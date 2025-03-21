<template>
  <div class="bg-gray-500 rounded-lg shadow-lg overflow-hidden">
    <div class="p-4">
      <!-- <div class="flex flex-row">
                <i class="uil uil-user pr-1 text-sm"></i>
                <p class="text-gray-700 font-semibold text-nowrap">
                  Id do usuário: {{ userId }}
                </p>
              </div> -->
      <!-- <div class="flex flex-row">
                <i class="uil uil-pen pr-1 text-sm"></i>
                <p class="text-gray-700 text-sm text-nowrap">
                  Id do post: {{ postId }}
                </p>
              </div> -->

      <h4 class="text-xl font-semibold">{{ title }}</h4>
      <p class="text-gray-600 mt-2">{{ body }}</p>
    </div>
  </div>
</template>

<script setup>
defineProps({
  title: String,
  description: String,
  userId: Number,
  postId: Number,
  body: String,
});
</script>
