<script setup>
import './LoginSignup.scss'

const props = defineProps({
    function: Function
})
</script>

<template>
    <div class="sidebar-inner__icon" @click="()=>props.function()">
        <svg height="13" width="13" xmlns="http://www.w3.org/2000/svg">
            <path d="M 1 1 L 12 12" style="fill:none;stroke:#232323;stroke-width:2" />
            <path d="M 12 1 L 1 12" style="fill:none;stroke:#232323;stroke-width:2" />
        </svg>
    </div>
    <div class="sidebar-inner__title">Sign in</div>
    <div class="sidebar-inner__form">
      <form>
        <div class="form-groups">
          <div class="form-group">
            <label class="form-label">Email Address <span>*</span></label>
            <input class="form-input" type="text">
          </div>
          <div class="form-group">
            <label class="form-label">Password <span>*</span></label>
            <input class="form-input" type="text">
          </div>
          <button class="form-btn">Login</button>
        </div>
      </form>
    </div>
    <p class="sidebar-inner__text text-center">Forget your password?</p>
    <button class="sidebar-inner__btn" style="background-color: var(--primary-color);">Create Account</button>
</template>