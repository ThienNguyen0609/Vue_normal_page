<script>
    import './Container.scss'
</script>

<template>
    <div class="my-container">
        <slot name="sidebar"></slot>
        <slot name="header"></slot>
        <slot name="body"></slot>
        <slot></slot>
    </div>
</template>