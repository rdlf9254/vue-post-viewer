<template>
  <div class="max-w-7xl">
    <h1 class="text-2xl font-bold mb-4">Tabela de Posts</h1>
    <view-switcher></view-switcher>
    <!-- <card-view v-if="view==='card'" :loading="loading" :data ="posts"></card-view> -->
    <table-view v-if="view === 'table'" :loading="loading" :data="posts" />
    <loading-spinner></loading-spinner>
  </div>
</template>

<script setup>
import { ref, onMounted } from "vue";
import api from "@/services/api";

import TableView from "@components/TableView.vue";
// import CardView from '@components/CardView.vue'
import ViewSwitcher from "@components/ViewSwitcher.vue";
import LoadingSpinner from "@components/LoadingSpinner.vue";

const posts = ref([]);

var loading = false;
var view = "table";

const fetchPosts = () => {
  api
    .get("/posts")
    .then((response) => {
      posts.value = response.data; // Atualiza os dados
    })
    .catch((error) => {
      console.error("Erro ao buscar os posts:", error);
    })
    .finally(() => {
      console.log("Requisição finalizada!");
    });
};

onMounted(fetchPosts);
</script>
