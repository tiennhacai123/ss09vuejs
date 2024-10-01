<template>
  <div>
    <h2>B1</h2>
    <label for="email">Nhập địa chỉ email:</label>
    <input id="email" v-model="email" type="email" placeholder="Nhập email của bạn" />

    <p>Địa chỉ email bạn đã nhập: {{ email }}</p>
  </div>
</template>

<script setup>
import { ref } from 'vue';

const email = ref("");
</script>
