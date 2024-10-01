<template>
  <div>
    <h2>B3</h2>
    <label for="birthday">Nhập ngày sinh:</label>
    <input id="birthday" v-model="birthday" type="date" />

    <p>Ngày sinh bạn đã nhập: {{ birthday }}</p>
  </div>
</template>

<script setup>
import { ref } from 'vue';

const birthday = ref("");
</script>
