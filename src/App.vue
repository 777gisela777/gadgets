<script setup>
import { reactive, provide } from 'vue'
import CategoryList from './components/CategoryList.vue'
import Cart from './components/Cart.vue'

const cart = reactive([])
const products = [
  { name: "Auriculars Wireless 🎧", price: 50 },
  { name: "Smartwatch ⌚", price: 120 },
  { name: "Teclat Mecànic ⌨️", price: 80 },
  { name: "Altaveu Bluetooth 🔊", price: 60 }
]

provide('cart', cart);
provide('products', products)
</script>

<template>
    <div class="app-container">
    <h1>Botiga de Gadgets</h1>
    <div class="content">
      <CategoryList />
      <Cart />
    </div>
  </div>
</template>

<style scoped>
:global(body) {
  margin: 0;
}

h1 {
  display: flex;
  justify-content: center;
  margin-top: 25px;
}

.app-container {
  margin: 0;
  background-color: azure;
  display: flex;
  flex-direction: column;
  min-height: 100vh;
  font-family: 'Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande', 'Lucida Sans Unicode', Geneva, Verdana, sans-serif;
}

.content {
  display: flex;
  flex-direction: row;
  justify-content: center;
  gap: 24px;
  margin: 50px 0;
  flex-wrap: wrap;
}
</style>
