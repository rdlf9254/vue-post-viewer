<template>
  <div class="max-w-7xl flex flex-col">
    <div class="header flex flex-row items-center gap-5">
      <div class="flex flex-nowrap items-center gap-4">
        <i class="uil uil-pen text-3xl"></i>
        <h1 class="text-3xl font-bold">Visualizador de Posts</h1>
      </div>

      <view-switcher></view-switcher>
    </div>
    <card-view
      class="w-full flex-1"
      :loading="loading"
      :data="posts"
    ></card-view>
    <table-view v-if="view === 'table'" :loading="loading" :data="posts" />
  </div>
</template>

<script setup>
import { ref, onMounted } from "vue";
import api from "@/services/api";

import TableView from "@components/TableView.vue";
import CardView from "@components/CardView.vue";
import ViewSwitcher from "@components/ViewSwitcher.vue";

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

onMounted(fetchPosts);
</script>
