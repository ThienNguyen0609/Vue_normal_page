<script setup>
import { ref } from 'vue';
import './assets/styles/app.scss'

import Container from './components/Container.vue';
import Header from './components/Header/Header.vue';
import Body from './components/Body/Body.vue';
import Footer from './components/Footer/Footer.vue';
import Sidebar from './components/Sidebar/Sidebar.vue';

const show = ref(false)
const sidebarNum = ref(0)

const ShoppingCart = (num) => {
  show.value = !show.value
  sidebarNum.value = num
}

</script>

<template>
  <Container>
    <template #sidebar>
      <Sidebar :show="show" :function="ShoppingCart" :sidebarNum="sidebarNum" />
    </template>
    <template #header>
      <Header :function="ShoppingCart"></Header>
    </template>
    <template #body>
      <Body></Body>
    </template>
    <template #>
      <Footer></Footer>
    </template>
  </Container>
</template>
