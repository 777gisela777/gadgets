<script setup>
import { inject } from 'vue'
import ProductItem from './ProductItem.vue'

const products = inject('products')
</script>

<template>
    <div class="category-list">
        <h2>Productes</h2>
        <div class="products">
            <ProductItem v-for="p in products" :key="p.name" :product="p" />
        </div>
    </div>
</template>

<style scoped>
.category-list {
    flex: 0 1 auto;
    font-family: 'Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande', 'Lucida Sans Unicode', Geneva, Verdana, sans-serif;
    padding: 20px;
    border: 1px solid #cbd5d1;
    border-radius: 10px;
    background-color: beige;
    width: fit-content;
    height: fit-content;
}

.products {
    display: flex;
    flex-direction: column;
    gap: 1rem;
}
</style>