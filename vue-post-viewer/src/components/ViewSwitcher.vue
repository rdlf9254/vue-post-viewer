<template>
  <div class="flex flex-row flex-nowrap items-center gap-4">
    <span class="text-sm text-gray-400">Visualização:</span>
    <div class="flex flex-row flex-nowrap items-center">
      <i
        @click="switchView('table')"
        class="uil uil-list-ul text-2xl pt-1 pb-1 pl-2 pr-2 border-t border-l border-b text-gray-400 border-gray-600 rounded-l-md cursor-pointer"
        :class="view === 'table' ? 'bg-gray-300 text-gray-600' : ''"
      ></i>
      <i
        @click="switchView('cards')"
        class="uil uil-apps text-2xl pt-1 pb-1 pl-2 pr-2 border-t border-r border-b text-gray-400 border-gray-600 rounded-r-md cursor-pointer"
        :class="view === 'cards' ? 'bg-gray-300 text-gray-600' : ''"
      ></i>
    </div>
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
