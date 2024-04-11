<script setup>
import './ShoppingCart.scss'

const props = defineProps({
    function: Function
})
</script>

<template>
    <div class="sidebar-inner__icon" @click="()=>props.function()">
        <svg height="13" width="13" xmlns="http://www.w3.org/2000/svg">
            <path d="M 1 1 L 12 12" style="fill:none;stroke:#232323;stroke-width:2" />
            <path d="M 12 1 L 1 12" style="fill:none;stroke:#232323;stroke-width:2" />
        </svg>
    </div>
    <div class="sidebar-inner__title">Shopping cart</div>
    <p class="sidebar-inner__text">3 items</p>
    <p class="sidebar-inner__text">Free shipping for all orders over $800.00!</p>
    <p class="sidebar-inner__text sidebar-inner__text-lastchild">Your cart is empty</p>
    <button class="sidebar-inner__btn" style="background-color: #e95144;">Checkout</button>
</template>