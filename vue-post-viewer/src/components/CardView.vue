<template>
  <div></div>
  <div
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
</template>

<script setup>
import Card from "@components/Card.vue";

defineProps({
  data: Array,
  loading: Boolean,
});
</script>
