<script setup>
import './MidHeader.scss'

const props = defineProps({
    function: Function
})
</script>

<template>
    <div class="header-inner__mid">
        <div class="container-wrapper">
            <div class="mid-header__inner">
                <div class="mid-header__inner-logo">
                    <div class="logo">ella</div>
                </div>
                <div class="mid-header__inner-text">
                    <div class="freeship-text">Free shipping on All Orders. No Minimum Purchase</div>
                    <div class="actions">
                        <div class="action" @click="()=>props.function(1)">
                            <img src="../../../assets/images/header/shopping-cart.png" alt="shopping-cart">
                            <div class="action-text text-responsive">Shopping Cart</div>
                            <div class="quantity">0</div>
                        </div>
                        <div class="action">
                            <div class="heart">
                                <svg height="17" width="18" xmlns="http://www.w3.org/2000/svg">
                                    <path d="M 9 4 Q 5 0 2 5 1 11 9 15" stroke="#323232" fill="none" stroke-width="1" />
                                    <path d="M 9 15 Q 17 11 16 5 14 0 9 4" stroke="#323232" fill="none" stroke-width="1" />
                                </svg>
                            </div>
                            <div class="action-text text-responsive">Shopping Cart</div>
                        </div>
                        <div class="action action-text" @click="()=>props.function(2)">Sign In or Create an account</div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>