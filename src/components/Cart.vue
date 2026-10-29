<script setup>
import { inject, computed } from 'vue'

const cart = inject('cart')

const total = computed(() =>
    cart.reduce((sum, p) => sum + p.price, 0)
)
</script>
<template>
    <div class="cart">
        <ul>
            <li v-for="item in cart" :key="item.name">{{ item.name }} - {{ item.price }}</li>
        </ul>
        <p class="total">Import total: {{ total }}</p>
    </div>
</template>
