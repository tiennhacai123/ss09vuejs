<template>
  <div>
    <h2>B6</h2>

    <label>
      <input type="checkbox" value="Đọc sách" v-model="hobbies" />
      Đọc sách
    </label>

    <label>
      <input type="checkbox" value="Nghe nhạc" v-model="hobbies" />
      Nghe nhạc
    </label>

    <label>
      <input type="checkbox" value="Chơi thể thao" v-model="hobbies" />
      Chơi thể thao
    </label>

    <label>
      <input type="checkbox" value="Du lịch" v-model="hobbies" />
      Du lịch
    </label>

    <p>Các sở thích bạn đã chọn: {{ hobbies.join(', ') }}</p>
  </div>
</template>

<script setup>
import { ref } from 'vue';

const hobbies = ref([]);
</script>
