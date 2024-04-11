<script setup>
import './BotHeader.scss'

const props = defineProps({
    function: Function
})
</script>

<template>
    <div class="header-inner__bot">
        <div class="nav-wrapper">
            <div class="container-wrapper">
                <div class="nav-inner">
                    <div class="nav-menu-icon" @click="()=>props.function(3)">
                        <svg height="17" width="25" xmlns="http://www.w3.org/2000/svg">
                            <path d="M 1 1 L 24 1" style="fill:none;stroke:#ffffff;stroke-width:2" />
                            <path d="M 1 8 L 24 8" style="fill:none;stroke:#ffffff;stroke-width:2" />
                            <path d="M 1 16 L 24 16" style="fill:none;stroke:#ffffff;stroke-width:2" />
                        </svg>
                    </div>
                    <div class="nav-links">
                        <div class="nav-link">
                            <a class="nav-link__text" href="#">New in</a>
                        </div>
                        <div class="nav-link">
                            <a class="nav-link__text" href="#">Trend</a>
                        </div>
                        <div class="nav-link">
                            <a class="nav-link__text" href="#">Collections</a>
                        </div>
                        <div class="nav-link">
                            <a class="nav-link__text" href="#">Lookbook</a>
                        </div>
                        <div class="nav-link">
                            <a class="nav-link__text" href="#">Demo</a>
                        </div>
                        <div class="nav-link">
                            <a class="nav-link__text" href="#">Shop instagram</a>
                        </div>
                        <div class="nav-link">
                            <a class="nav-link__text" href="#">Blog</a>
                        </div>
                        <div class="nav-link">
                            <a class="nav-link__text" href="#">Brands</a>
                        </div>
                        <div class="nav-link">
                            <a class="nav-link__text" href="#">FAQS</a>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>