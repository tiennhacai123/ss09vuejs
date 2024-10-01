<template>
  <div>
    <h2>B4</h2>
    <label for="progress">Tiến độ hoàn thành:</label>
    <input id="progress" v-model="progress" type="range" min="0" max="100" />

    <p>Tiến độ: {{ progress }}%</p>
  </div>
</template>

<script setup>
import { ref } from 'vue';

const progress = ref(0);
</script>
