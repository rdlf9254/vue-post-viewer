<template>
  <div class="max-w-7xl flex flex-col pt-4">
    <div
      class="header flex flex-row items-center gap-5 pt-3 pb-3 pl-4 pr-4 border"
    >
      <div class="flex flex-nowrap items-center gap-4">
        <i class="uil uil-pen text-3xl"></i>
        <h1 class="text-3xl font-bold">Visualizador de Posts</h1>
      </div>

      <view-switcher @switch="setView"></view-switcher>
    </div>
    <div
      v-if="loading"
      class="flex flex-col items-center justify-center py-6 text-gray-600 dark:text-gray-300"
    >
      <loading-spinner class="mb-2" />
      <p class="mt-2 text-lg font-semibold">Carregando...</p>
    </div>

    <card-view
      v-else-if="!loading && view === 'cards'"
      :data="posts"
    ></card-view>
    <table-view v-else-if="!loading && view === 'table'" :data="posts" />
  </div>
</template>

<script setup>
import { ref, onMounted } from "vue";
import api from "@/services/api";

import TableView from "@components/TableView.vue";
import CardView from "@components/CardView.vue";
import ViewSwitcher from "@components/ViewSwitcher.vue";
import LoadingSpinner from "@components/LoadingSpinner.vue"

const posts = ref([]);
const loading = ref(false);
const view = ref("table");

const fetchPosts = () => {
  loading.value = true;

  api
    .get("/posts")
    .then((response) => {
      posts.value = response.data;
    })
    .catch((error) => {
      console.error("Erro ao buscar os posts:", error);
    })
    .finally(() => {
      loading.value = false;
      console.log("Requisição finalizada!");
    });
};

const setView = (newView) => {
  view.value = newView;
  console.log("Evento recebido:", newView);
};

onMounted(fetchPosts);
</script>
