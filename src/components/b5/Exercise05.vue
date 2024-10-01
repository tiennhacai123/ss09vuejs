<template>
  <div>
    <h2>B5</h2>

    <label>
      <input type="radio" v-model="gender" value="Nam" />
      Nam
    </label>

    <label>
      <input type="radio" v-model="gender" value="Nữ" />
      Nữ
    </label>

    <label>
      <input type="radio" v-model="gender" value="Khác" />
      Khác
    </label>

    <p>Giới tính bạn đã chọn: {{ gender }}</p>
  </div>
</template>

<script setup>
import { ref } from "vue";

const gender = ref("");
</script>
