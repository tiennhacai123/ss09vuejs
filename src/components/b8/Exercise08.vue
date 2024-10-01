<template>
  <div>
    <h2>B8</h2>
    <form @submit.prevent="registerUser">
      <div>
        <label for="name">Tên:</label>
        <input id="name" v-model="user.name" required />
      </div>

      <div>
        <label for="email">Email:</label>
        <input id="email" v-model="user.email" type="email" required />
      </div>

      <div>
        <label for="password">Mật khẩu:</label>
        <input id="password" v-model="user.password" type="password" required />
      </div>

      <div>
        <label for="confirmPassword">Nhập lại mật khẩu:</label>
        <input id="confirmPassword" v-model="user.confirmPassword" type="password" required />
      </div>

      <button type="submit">Đăng ký</button>
    </form>
  </div>
</template>

<script setup>
import { ref } from 'vue';

const user = ref({
  name: '',
  email: '',
  password: '',
  confirmPassword: ''
});

const registerUser = () => {
  console.log(user.value);
  user.value = {
    name: '',
    email: '',
    password: '',
    confirmPassword: ''
  };
};
</script>
