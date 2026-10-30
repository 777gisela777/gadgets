<script setup>
defineProps(['item'])
</script>

<template>
    <li class="cart-item">{{ item.name }} - {{ item.price }}€</li>
</template>

<style scoped>
    .cart-item {
        font-family: 'Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande', 'Lucida Sans Unicode', Geneva, Verdana, sans-serif;
    }
</style>