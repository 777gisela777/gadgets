<script setup>
import { inject, computed } from 'vue'
import CartItem from './CartItem.vue'

const cart = inject('cart')

const count = computed(() => cart.length)

const total = computed(() =>
    cart.reduce((sum, p) => sum + p.price, 0)
)

const emptyCart = () => {
    const empty = confirm("Segur que vols eliminar tots els productes del carret?")
    if (empty) {
        cart.splice(0)
    }
}
</script>

<template>
    <div class="cart">
        <h2>Carret</h2>
        <ul>
            <CartItem
                v-for="item in cart"
                :key="item.name"
                :item="item"
            />
        </ul>
        <button @click="emptyCart">Buidar el carret</button>
        <p class="total">Import total: {{ total }}€</p>
        <p class="count">Productes al carret: {{ count }}</p>
    </div>
</template>

<style scoped>
    button {
        padding: 5px 12px;
        border: 0;
        margin-left: 0px;
        margin-top: 20px;
        border-radius: 10px;
        background: green;
        color: #fff;
        font: inherit;
    }

    button:hover {
        background: rgb(2, 96, 2);
    }

    .cart {
        flex: 0 1 auto;
        font-family: 'Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande', 'Lucida Sans Unicode', Geneva, Verdana, sans-serif;
        padding: 20px;
        border: 1px solid #cbd5d1;
        border-radius: 10px;
        background-color: beige;
        width: fit-content;
        height: fit-content;
    }

    ul {
        list-style: none;
        padding-left: 0;
        margin-left: 0;
        display: flex;
        flex-direction: column;
        gap: 10px;
    }
</style>