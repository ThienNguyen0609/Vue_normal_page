<script setup>
import './Header.scss'
import MidHeader from './MidHeader/MidHeader.vue';
import TopHeader from './TopHeader/TopHeader.vue';
import BotHeader from './BotHeader/BotHeader.vue';

const props = defineProps({
    function: Function
})
</script>

<template>
    <header class="wrapper">
        <div class="header-inner">
            <TopHeader />
            <MidHeader :function="props.function" />
            <BotHeader :function="props.function" />
        </div>
    </header>
</template>