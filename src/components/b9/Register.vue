<template>
  <div>
    <h2>B9</h2>
    <form @submit.prevent="handleSubmit">
      <div>
        <label for="studentName">Tên sinh viên:</label>
        <input
          id="studentName"
          v-model="form.studentName"
          required
          ref="studentNameInput"
        />
      </div>

      <div>
        <label for="email">Email:</label>
        <input
          id="email"
          v-model="form.email"
          type="email"
          required
        />
        <span v-if="emailExists" class="error">Email đã tồn tại.</span>
      </div>

      <div>
        <label for="password">Mật khẩu:</label>
        <input
          id="password"
          v-model="form.password"
          type="password"
          required
        />
      </div>

      <div>
        <label for="address">Địa chỉ:</label>
        <input
          id="address"
          v-model="form.address"
          required
        />
      </div>

      <button type="submit">Đăng ký</button>
    </form>
    <p v-if="successMessage">{{ successMessage }}</p>
  </div>
</template>

<script setup>
import { ref } from 'vue';

const form = ref({
  studentName: '',
  email: '',
  password: '',
  address: ''
});

const successMessage = ref('');
const emailExists = ref(false);

const handleSubmit = () => {
  if (!form.value.studentName || !form.value.email || !form.value.password) {
    alert("Tên sinh viên, Email và Mật khẩu không được để trống.");
    return;
  }

  const existingUsers = JSON.parse(localStorage.getItem('users')) || [];
  emailExists.value = existingUsers.some(user => user.email === form.value.email);

  if (emailExists.value) {
    return;
  }

  existingUsers.push({ ...form.value });
  localStorage.setItem('users', JSON.stringify(existingUsers));

  // Clear form fields
  form.value.studentName = '';
  form.value.email = '';
  form.value.password = '';
  form.value.address = '';

  successMessage.value = "Đăng ký tài khoản thành công.";

  setTimeout(() => {
    document.getElementById('studentName').focus();
  }, 0);
};
</script>

<style scoped>
.error {
  color: red;
  font-size: 0.8em;
}
</style>
