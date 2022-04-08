<template>
  <input
    type="text"
    class="form-control mb-2"
    placeholder="İş Girişi Yapınız"
    @keydown.enter="ekle"
  />
</template>

<script setup>
const props = defineProps({ kayit: Function });

const ekle = event => {
  props.kayit(event.target.value);
  event.target.value = "";
};
</script>
