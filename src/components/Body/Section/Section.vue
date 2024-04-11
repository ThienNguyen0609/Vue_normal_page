<script setup>
import './Section.scss'

import ProductItem from './ProductItem/ProductItem.vue';
import { onMounted, ref } from 'vue'
import { FontAwesomeIcon } from '@fortawesome/vue-fontawesome'
import { faInstagram } from '@fortawesome/free-brands-svg-icons';
import { faAngleLeft, faAngleRight } from '@fortawesome/free-solid-svg-icons';
import { products } from '../../../context/product'

const galleryRef = ref(null)
const condition = ref(false)

const handleClick = (action) => {
    if(action === "next") galleryRef.value.scrollLeft += 235
    else galleryRef.value.scrollLeft -= 235
}

onMounted(() => {
    galleryRef.value?.offsetWidth < 1170 ? condition.value = true : condition.value = false
})
</script>

<template>
    <section class="section-wrapper">
        <div class="section-inner">
            <div class="product-wrapper">
                <div class="container-wrapper">
                    <div class="product-inner">
                        <div class="sub-banner">
                            <div class="sub-banner__item">
                                <div class="sub-banner__image">
                                    <img src="../../../assets/images/sub-banner/editor.png" alt="image">
                                </div>
                                <div class="sub-banner__overlay">
                                    <img src="../../../assets/images/sub-banner/editor_overlay.png" alt="img">
                                </div>
                                <div class="sub-banner__text">Editor's Pick</div>
                            </div>
                            <div class="sub-banner__item">
                                <div class="sub-banner__image">
                                    <img src="../../../assets/images/sub-banner/shoes.png" alt="image">
                                </div>
                                <div class="sub-banner__overlay">
                                    <img src="../../../assets/images/sub-banner/shoes_overlay.png" alt="img">
                                </div>
                                <div class="sub-banner__text">Shoes</div>
                            </div>
                            <div class="sub-banner__item">
                                <div class="sub-banner__image">
                                    <img src="../../../assets/images/sub-banner/accessories.png" alt="image">
                                </div>
                                <div class="sub-banner__overlay">
                                    <img src="../../../assets/images/sub-banner/accessories_overlay.png" alt="img">
                                </div>
                                <div class="sub-banner__text">Accessories</div>
                            </div>
                        </div>
                        <div class="product">
                            <div class="product-text">
                                <div class="product__text-title">
                                    New Arrivals
                                </div>
                                <p>View all</p>
                            </div>
                            <div class="product-display">
                                <ProductItem v-for="product in products" :image="product.image" :title="product.title" :description="product.description" :price="product.price" :categories="product.categories" />
                            </div>
                            <div class="product-btn">Show more</div>
                        </div>
                    </div>
                </div>
            </div>
            <div class="gallery-wrapper">
                <div class="container-wrapper">
                    <div class="gallery-inner">
                        <div class="gallery-title">
                            <FontAwesomeIcon :icon="faInstagram" class="instagram-icon" />
                            <span>#Ella On Instagram</span>
                        </div>
                        <div class="gallery-description">
                            Phasellus lorem malesuada ligula pulvinar commodo maecenas
                        </div>
                        <div class="gallery-display">
                            <div v-if="condition === true" class="gallery-display__btn left-btn" @click="()=>handleClick('prev')"><FontAwesomeIcon :icon="faAngleLeft" /></div>
                            <div v-if="condition === true" class="gallery-display__btn right-btn" @click="()=>handleClick('next')"><FontAwesomeIcon :icon="faAngleRight" /></div>
                            <div class="gallery-display__list" ref="galleryRef">
                                <div class="gallery-display__item">
                                    <img src="../../../assets/images/gallery/gallery_1.png" alt="image">
                                </div>
                                <div class="gallery-display__item">
                                    <img src="../../../assets/images/gallery/gallery_2.png" alt="image">
                                </div>
                                <div class="gallery-display__item">
                                    <img src="../../../assets/images/gallery/gallery_3.png" alt="image">
                                </div>
                                <div class="gallery-display__item">
                                    <img src="../../../assets/images/gallery/gallery_4.png" alt="image">
                                </div>
                                <div class="gallery-display__item">
                                    <img src="../../../assets/images/gallery/gallery_5.png" alt="image">
                                </div>
                            </div>
                        </div>
                        <div class="gallery-btn">View Gallery</div>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>