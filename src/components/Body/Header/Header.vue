<script setup>
import './Header.scss'
import { onMounted, ref } from 'vue'

let setTime
const index = ref(1)
const nextIndex = ref(0)
const prevIndex = ref(0)

const intervalManager = (flag, func, time) => {
    if(flag) setTime = setInterval(func, time)
    else clearInterval(setTime)
}
const handleCarousel = (action, i) => {
    intervalManager(false)
    action === "next" ? nextIndex.value = i : prevIndex.value = i
    setTimeout(()=>{
        nextIndex.value = prevIndex.value = 0
        switch (action) {
            case "prev":
                index.value === 1 ? (index.value = 3) : (index.value--);
                return
            case "next":
                index.value === 3 ? (index.value = 1) : (index.value++);
                return
        }
    }, 500)
    intervalManager(true, () => handleCarousel("next", index.value), 5000)
}
onMounted(() => {
    intervalManager(true, () => handleCarousel("next", index.value), 5000)
})
</script>

<template>
    <header>
        <div class="carousel-wrapper">
            <div class="carousel-inner">
                <div class="carousel-inner__arrow-btn prev-arrow-btn" @click="()=>handleCarousel('prev', index)">
                    <svg height="29" width="29" xmlns="http://www.w3.org/2000/svg">
                        <path d="M 20 1 L 5 14.5 L 20 28" style="fill:none;stroke:#232323;stroke-width:3" />
                    </svg>
                </div>
                <div class="carousel-inner__images">
                    <div class="carousel-inner__image" 
                        :class="{ 
                            'active': nextIndex === 1 || nextIndex === 3 || prevIndex === 1 || prevIndex === 2 || index === 1,
                            'animation-hide-to-left': nextIndex === 1,
                            'animation-hide-to-right': prevIndex === 1, 
                            'animation-show-from-left': prevIndex === 2,
                            'animation-show-from-right': nextIndex === 3,
                        }"
                    >
                        <img src="../../../assets/images/carousel/carousel1.png" alt="carousel-image">
                    </div>
                    <div class="carousel-inner__image" 
                        :class="{ 
                            'active': nextIndex === 2 || nextIndex === 1 || prevIndex === 2 || prevIndex === 3 || index === 2,
                            'animation-hide-to-left': nextIndex === 2,
                            'animation-hide-to-right': prevIndex === 2, 
                            'animation-show-from-left': prevIndex === 3,
                            'animation-show-from-right': nextIndex === 1,
                        }"
                    >
                        <img src="../../../assets/images/carousel/carousel2.png" alt="carousel-image">
                    </div>
                    <div class="carousel-inner__image" 
                        :class="{ 
                            'active': nextIndex === 3 || nextIndex === 2 || prevIndex === 3 || prevIndex === 1 || index === 3,
                            'animation-hide-to-left': nextIndex === 3,
                            'animation-hide-to-right': prevIndex === 3, 
                            'animation-show-from-left': prevIndex === 1,
                            'animation-show-from-right': nextIndex === 2,
                        }"
                    >
                        <img src="../../../assets/images/carousel/carousel3.png" alt="carousel-image">
                    </div>
                </div>
                <div class="carousel-inner__arrow-btn next-arrow-btn" @click="()=>handleCarousel('next', index)">
                    <svg height="29" width="29" xmlns="http://www.w3.org/2000/svg">
                        <path d="M 9 1 L 24 14.5 L 9 28" style="fill:none;stroke:#232323;stroke-width:3" />
                    </svg>
                </div>
                <div class="carousel-inner__text"></div>
            </div>
        </div>
    </header>
</template>