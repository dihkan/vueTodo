<template>
  <ul class="list-group ">
    <li
      class="list-group-item d-flex justify-content-between align-items-center"
      v-for="todo in liste"
      :key="todo"
    >
      <input
        type="checkbox"
        :key="todo.id"
        :id="todo.id"
        v-model="todo.is_completed"
      />
      <div style="width:80%">
        {{ todo.todo }}
      </div>

      <button class="btn btn-danger" @click="sil(this)">
        <i class="bi bi-trash3-fill"></i>
      </button>
    </li>
  </ul>
</template>

<script setup>
const props = defineProps({
  liste: Array
});
const sil = event => {
  console.log(event.target.id);
};
</script>
