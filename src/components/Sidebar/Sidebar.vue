<script setup>
import { ref } from 'vue';
import './Sidebar.scss'

import ShoppingCart from './ShoppingCart/ShoppingCart.vue'
import LoginSignup from './LoginSignup/LoginSignup.vue';
import NavSidebar from './NavSidebar/NavSidebar.vue';

const props = defineProps({
    show: Boolean,
    function: Function,
    sidebarNum: Number
})
const close = ref(false)

const setClose = () => {
    close.value = !close.value
}
const hideShoppingCart = () => {
  setClose()
  setTimeout(()=>{
    props.function();
    setClose()
  }, 500)
}
</script>

<template>
    <div v-if="props.show" class="sidebar-wrapper">
        <div class="sidebar-inner">
            <div v-if="props.sidebarNum !== 3" class="sidebar-content show-right-sidebar" :class="{ 'hide-right-sidebar': close }">
                <div class="sidebar-content__inner right-sidebar">
                    <ShoppingCart v-if="props.sidebarNum === 1" :function="hideShoppingCart" />
                    <LoginSignup v-else-if="props.sidebarNum === 2" :function="hideShoppingCart" />
                </div>
            </div>
            <div v-else class="sidebar-content show-left-sidebar" :class="{ 'hide-left-sidebar': close }">
                <div class="sidebar-content__inner left-sidebar">
                    <NavSidebar :function="hideShoppingCart" />
                </div>
            </div>
        </div>
    </div>
</template>