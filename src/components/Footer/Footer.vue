<script setup>
import './Footer.scss'
import { FontAwesomeIcon } from '@fortawesome/vue-fontawesome'
import { faFacebookF, faTwitter, faInstagram, faPinterestP, faSnapchatGhost } from '@fortawesome/free-brands-svg-icons'
</script>

<template>
    <footer class="footer-wrapper">
        <div class="footer-inner">
            <div class="top-footer">
                <div class="container-wrapper">
                    <div class="top-inner">
                        <div class="list">
                            <div class="title">Shop</div>
                            <a href="#" class="item text">New In</a>
                            <a href="#" class="item text">Women</a>
                            <a href="#" class="item text">Men</a>
                            <a href="#" class="item text">Shoes</a>
                            <a href="#" class="item text">Bags & Accessories</a>
                            <a href="#" class="item text">Top Brands</a>
                            <a href="#" class="item text">Sale & Special Offers</a>
                            <a href="#" class="item text">Lookbook</a>
                        </div>
                        <div class="list">
                            <div class="title">Information</div>
                            <a href="#" class="item text">About</a>
                            <a href="#" class="item text">Customer Service</a>
                            <a href="#" class="item text">Reward Program</a>
                            <a href="#" class="item text">Shipping & Returns</a>
                            <a href="#" class="item text">Privacy Policy</a>
                            <a href="#" class="item text">Terms & Conditions</a>
                            <a href="#" class="item text">Blog</a>
                        </div>
                        <div class="list">
                            <div class="title">Customer Service</div>
                            <a href="#" class="item text">Search Terms</a>
                            <a href="#" class="item text">Advanced Search</a>
                            <a href="#" class="item text">Orders and Returns</a>
                            <a href="#" class="item text">Contact Us</a>
                            <a href="#" class="item text">Theme FQAs</a>
                            <a href="#" class="item text">Consultant</a>
                            <a href="#" class="item text">Store Location</a>
                        </div>
                        <div class="form">
                            <div class="title">Newletter Sign Up</div>
                            <div class="text">Sign up for exclusive updates, new arrivals & insider only discounts</div>
                            <div class="form-group">
                                <input type="text" placeholder="Email Address">
                                <button>Submit</button>
                            </div>
                            <div class="social-media">
                                <div class="social-media__item">
                                    <FontAwesomeIcon :icon="faFacebookF" style="height: 14px; width: 8px;"/>
                                </div>
                                <div class="social-media__item">
                                    <FontAwesomeIcon :icon="faTwitter" style="height: 12px; width: 14px;" />
                                </div>
                                <div class="social-media__item">
                                    <FontAwesomeIcon :icon="faInstagram" style="height: 16px; width: 16px;" />
                                </div>
                                <div class="social-media__item">
                                    <FontAwesomeIcon :icon="faPinterestP" style="height: 16px; width: 12px;" />
                                </div>
                                <div class="social-media__item">
                                    <FontAwesomeIcon :icon="faSnapchatGhost" style="height: 16px; width: 17px;" />
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
            <div class="bot-footer">
                <div class="container-wrapper">
                    <div class="bot-inner">
                        <div class="text">
                            <p>© 2014 Ella Demo. All Rights Reserved. Powered by Shopify.</p>
                            <p>Shopify Themes by HaloThemes.com</p>
                        </div>
                        <div class="cart">
                            <div class="cart-item">
                                <img src="../../assets/images/cart/first_cart.png" alt="cart-image">
                            </div>
                            <div class="cart-item">
                                <img src="../../assets/images/cart/second_cart.png" alt="cart-image">
                            </div>
                            <div class="cart-item">
                                <img src="../../assets/images/cart/third_cart.png" alt="cart-image">
                            </div>
                            <div class="cart-item">
                                <img src="../../assets/images/cart/forth_cart.png" alt="cart-image">
                            </div>
                            <div class="cart-item">
                                <img src="../../assets/images/cart/fifth_cart.png" alt="cart-image">
                            </div>
                            <div class="cart-item">
                                <img src="../../assets/images/cart/sixth_cart.png" alt="cart-image">
                            </div>
                            <div class="cart-item">
                                <img src="../../assets/images/cart/seventh_cart.png" alt="cart-image">
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </footer>
</template>