<script setup>
import './NavSidebar.scss'
import { FontAwesomeIcon } from '@fortawesome/vue-fontawesome'
import { faPlus } from '@fortawesome/free-solid-svg-icons'
import { ref } from 'vue';

const props = defineProps({
    function: Function
})

const show = ref(false)
const action = ref(false)
const handleDropdown = (bool) => {
    if(bool) {
        action.value = true
        setTimeout(() => {
            action.value = false
            show.value = !show.value
        }, 300)
    }
    else show.value = !show.value
}
</script>

<template>
    <div class="sidebar-inner__icon" @click="()=>props.function()">
        <svg height="13" width="13" xmlns="http://www.w3.org/2000/svg">
            <path d="M 1 1 L 12 12" style="fill:none;stroke:#ffffff;stroke-width:2" />
            <path d="M 12 1 L 1 12" style="fill:none;stroke:#ffffff;stroke-width:2" />
        </svg>
    </div>
    <div class="sidebar-inner__logo">ella</div>
    <div class="sidebar-inner__nav-links">
        <div class="sidebar-inner__nav-link">
            <a href="#" class="nav-link__inner">New in</a>
        </div>
        <div class="sidebar-inner__nav-link">
            <a href="#" class="nav-link__inner">Trend</a>
        </div>
        <div class="sidebar-inner__nav-link">
            <a href="#" class="nav-link__inner">Collections</a>
        </div>
        <div class="sidebar-inner__nav-link">
            <a href="#" class="nav-link__inner">Lookbook</a>
        </div>
        <div class="sidebar-inner__nav-link">
            <a href="#" class="nav-link__inner">Demo</a>
        </div>
        <div class="sidebar-inner__nav-link">
            <a href="#" class="nav-link__inner">Shop instagram</a>
        </div>
        <div class="sidebar-inner__nav-link">
            <div class="nav-link__inner" @click="()=>handleDropdown(show)">Blog</div>
            <div v-if="show" class="nav-link__dropdown hd-show-dropdown" :class="{ 'hd-hide-dropdown': action }">
                <a class="nav-link__dropdown-item">+ Blog Default Layout</a>
                <a class="nav-link__dropdown-item">+ Blog with Small Image<br/>and Left Sidebar</a>
                <a class="nav-link__dropdown-item">+ Blog Mansory</a>
                <a class="nav-link__dropdown-item">+ Blog Full-width</a>
                <a class="nav-link__dropdown-item">+ Blog Post with LookBook</a>
                <a class="nav-link__dropdown-item">+ Blog Post with Product Widget</a>
            </div>
        </div>
        <div class="sidebar-inner__nav-link">
            <a href="#" class="nav-link__inner">Brands</a>
        </div>
        <div class="sidebar-inner__nav-link">
            <a href="#" class="nav-link__inner">FAQS</a>
        </div>
    </div>
</template>