<script setup>
import { inject, defineProps } from 'vue'

const props = defineProps(['product']) //es defineix com a const perquè al script setup l'utilitzarem a la funció addToCart
//defineProps(['product'])  //aquesta es podria fer si no l'utilitzessim a cap altra funció del script setup
const cart = inject('cart')

const addToCart = () => {
    cart.push(props.product)
    alert(`${props.product.name} afegit al carret!`)
}
</script>

<template>
    <div class="product-item">
        <div class="product-info">
            <span class="name">{{ product.name }}</span> - 
            <span class="price">{{ product.price }}€</span>
        </div>
        <button @click="addToCart">Afegir al carret</button>
    </div>
</template>

<style scoped>
    div {
        font-family: 'Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande', 'Lucida Sans Unicode', Geneva, Verdana, sans-serif;
    }

    * {
        display: flex;
    }

    button {
        padding: 5px 12px;
        border: 0;
        margin-left: 20px;
        border-radius: 10px;
        background: green;
        color: #fff;
        font: inherit;
    }

    button:hover {
        background: rgb(2, 96, 2);
    }
</style>