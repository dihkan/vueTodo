<template>
  <div>
    <div class="bg-danger text-white p-2 m-2">
      Tamamlanmamış iş sayısı : {{ uncompletedLength }}
    </div>
    <div class="bg-success text-white p-2 m-2">
      Tamamlanmış iş sayısı : {{ completedLength }}
    </div>
  </div>
</template>

<script setup>
import { computed } from "vue";
const props = defineProps({
  liste: Array
});

const completedLength = computed(
  () => props.liste.filter(item => item.is_completed).length
);
const uncompletedLength = computed(
  () => props.liste.filter(item => !item.is_completed).length
);
</script>
