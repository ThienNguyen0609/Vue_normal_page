<script setup>
import './ProductItem.scss'

import { onMounted, ref } from 'vue'

const show = ref(false)
const innerHTML = ref("XS")
const elementRef = ref(null)

const getSize = (event, size) => {
    const offsetWidth = event.target.offsetWidth
    const offsetLeft = event.target.offsetLeft
    const eOffsetWidth = elementRef.value.offsetWidth

    elementRef.value.style.left = `${offsetLeft - ((eOffsetWidth - offsetWidth)/2)}`+'px'
    innerHTML.value = size
}
const product = defineProps({
    image: String,
    title: String,
    description: String,
    price: String,
    categories: Array
})
</script>

<template>
    <div class="product-display__item">
        <div class="product-display__svg-icon">
            <svg height="17" width="18" xmlns="http://www.w3.org/2000/svg">
                <path d="M 9 4 Q 5 0 2 5 1 11 9 15" stroke="#323232" fill="none" stroke-width="1" />
                <path d="M 9 15 Q 17 11 16 5 14 0 9 4" stroke="#323232" fill="none" stroke-width="1" />
            </svg>
        </div>
        <div class="product-display__image">
            <img :src="`./src/assets/images/product/${product.image}.png`" alt="image">
            <div class="add-to-cart-action">
                <button class="add-to-cart__btn" @click="()=>{show = true}">Add To Cart</button>
            </div>
            <div class="submit-action" :class="{ 'slide-up': show }">
                <div class="submit__close-icon" @click="()=>{show = false}">
                    <svg height="13" width="13" xmlns="http://www.w3.org/2000/svg">
                        <path d="M 1 1 L 12 12" style="fill:none;stroke:#232323;stroke-width:2" />
                        <path d="M 12 1 L 1 12" style="fill:none;stroke:#232323;stroke-width:2" />
                    </svg>
                </div>
                <div class="submit__size">
                    <p>Size: <span v-html="innerHTML"></span></p>
                </div>
                <div class="submit__size-choose">
                    <p class="style-size" @click="(e)=>getSize(e, 'XS')">XS</p>
                    <p class="style-size" @click="(e)=>getSize(e, 'S')">S</p>
                    <p class="style-size" @click="(e)=>getSize(e, 'M')">M</p>
                    <p class="style-size" @click="(e)=>getSize(e, 'L')">L</p>
                    <p class="style-size" @click="(e)=>getSize(e, 'XL')">XL</p>
                    <p class="style-size" @click="(e)=>getSize(e, '2X')">2X</p>
                    <div ref="elementRef" class="underline"></div>
                </div>
                <button class="submit__btn">submit</button>
            </div>
        </div>
        <div class="product-display__text">
            <div class="product-display__title">{{ product.title }}</div>
            <div class="product-display__description">{{ product.description }}
            </div>
            <div class="product-display__price">{{ product.price }}</div>
            <div class="product-display__categories">
                <div v-for="category in product.categories" class="product-display__category">
                    <div class="product-display__category-inner" :class="`category-${category}-color`"></div>
                </div>
            </div>
        </div>
    </div>
</template>