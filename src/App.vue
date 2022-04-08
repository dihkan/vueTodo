<template>
  <div class="container mt-3">
    <div class="col-md-5 mx-auto">
      <div
        class="border border-3 shadow-md rounded-3 overflow-hidden p-4 border-success bgcolor"
      >
        <h4 class="text-center yazi ">{{ title }}</h4>

        <addItem :kayit="kayit" />
        <listem :liste="todoList"></listem>
        <sonuc :liste="todoList"></sonuc>
      </div>
    </div>
  </div>
</template>

<script setup>
import addItem from "./components/addItem.vue";
import listem from "./components/listem.vue";
import sonuc from "./components/sonuc.vue";

import { ref } from "vue";
const title = ref("İlk Todo Uygulaması");

const todoList = ref([]);

const kayit = todoText => {
  todoList.value.push({
    id: new Date().getTime(),
    todo: todoText,
    is_completed: false
  });
};
</script>
