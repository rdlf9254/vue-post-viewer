<script setup>
import { ref, onMounted } from 'vue'
import TableView from '@/components/TableView.vue'
import LoadingSpinner from '@/components/LoadingSpinner.vue'


</script>

<template>
  <div class="">
    <div class="max-w-7xl border-orange-100 border w-max h-screen">

      <h1 class="text-2xl font-bold mb-4">Tabela de Posts</h1>
      <table-view  />
      <loading-spinner></loading-spinner>

    </div>
  </div>
</template>
