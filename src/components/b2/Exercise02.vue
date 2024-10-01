<template>
  <div>
    <h2>B2</h2>
    <label for="color">Chọn màu sắc:</label>
    <input id="color" v-model="color" type="color" />

    <p>Mã màu bạn đã chọn: {{ color }}</p>
  </div>
</template>

<script setup>
import { ref } from 'vue';

const color = ref("#000000");
</script>
