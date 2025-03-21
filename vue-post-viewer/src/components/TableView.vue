<template>
  <table class="table-auto">
    <!-- <thead>
      <tr>
        <th>index</th>
        <th>userId</th>
        <th>id</th>
        <th>title</th>
        <th>body</th>
      </tr>
    </thead> -->

    <!-- <tbody>
      <tr v-for="item,i in data">
        <td>{{ i }}</td>
        <td v-for="dt in item">{{ dt }}</td>
      </tr>
    </tbody> -->
    <tbody>
      <tr v-for="item,i in data" class="border border-stone-500">
        <td>
          <div class=" flex-col">
            <p>Id do usuário: {{ item.userId }}</p>
            <p>Id do post: {{ item.id }}</p>
          </div>
          </td>
        <td>
          <div class=" flex-col">
            <p>Título: {{ item.title }}</p>
            <p>{{ item.body }}</p>
          </div>
          </td>
      </tr>
    </tbody>
  </table>
</template>

<script setup>
import { defineProps } from "vue";

const props = defineProps({
  data: Array,
  loading: Boolean,
});
</script>
