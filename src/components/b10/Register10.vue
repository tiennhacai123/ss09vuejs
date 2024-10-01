<template>
  <div>
    <h2>B10</h2>
    <form @submit.prevent="handleLogin">
      <div>
        <label for="email">Email:</label>
        <input id="email" v-model="credentials.email" type="email" required />
      </div>

      <div>
        <label for="password">Mật khẩu:</label>
        <input id="password" v-model="credentials.password" type="password" required />
      </div>

      <button type="submit">Đăng nhập</button>
    </form>
    <p v-if="message">{{ message }}</p>
  </div>
</template>

<script setup>
import { ref } from 'vue';

const credentials = ref({
  email: '',
  password: ''
});

const message = ref('');

const handleLogin = () => {
  if (!credentials.value.email || !credentials.value.password) {
    alert("Email và Mật khẩu không được để trống.");
    return;
  }

  const existingUsers = JSON.parse(localStorage.getItem('users')) || [];

  const user = existingUsers.find(
    (user) => user.email === credentials.value.email && user.password === credentials.value.password
  );

  if (user) {
    message.value = "Đăng nhập thành công";
  } else {
    message.value = "Đăng nhập thất bại";
  }
};
</script>

<style scoped>
</style>
