<template>
  <div>
    <h2>B7</h2>
    <form @submit.prevent="addProduct">
      <div>
        <label for="productCode">Mã sản phẩm:</label>
        <input id="productCode" v-model="product.code" required />
      </div>

      <div>
        <label for="productName">Tên sản phẩm:</label>
        <input id="productName" v-model="product.name" required />
      </div>

      <div>
        <label for="productPrice">Giá:</label>
        <input id="productPrice" v-model="product.price" type="number" required />
      </div>

      <div>
        <label for="productQuantity">Số lượng:</label>
        <input id="productQuantity" v-model="product.quantity" type="number" required />
      </div>

      <button type="submit">Thêm mới</button>
    </form>
  </div>
</template>

<script setup>
import { ref } from 'vue';

const product = ref({
  code: '',
  name: '',
  price: 0,
  quantity: 0
});

const addProduct = () => {
  console.log(product.value);
  // Reset form after submission if needed
  product.value = {
    code: '',
    name: '',
    price: 0,
    quantity: 0
  };
};
</script>
