<template>
  <div class="flex flex-row flex-nowrap">
    <i
      @click="switchView('table')"
      class="uil uil-list-ul text-2xl pt-1 pb-1 pl-2 pr-2 border rounded-l-md cursor-pointer"
      :class="view === 'table' ? 'bg-blue-950':''"
    ></i>
    <i
      @click="switchView('cards')"
      class="uil uil-apps text-2xl pt-1 pb-1 pl-2 pr-2 border rounded-r-md cursor-pointer"
      :class="view === 'cards' ? 'bg-blue-950':''"
    ></i>
  </div>
</template>

<script setup>
import { ref } from "vue";

const view = ref("table");
const emit = defineEmits();

const switchView = (value) => {
  view.value = value;
  emit("switch", view.value);
};
</script>
