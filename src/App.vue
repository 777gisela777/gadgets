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
.app-container {
  display: flex;
  flex-direction: column;
}
</style>
