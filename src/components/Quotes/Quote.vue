<template>
    <div class="quote">
        <slot></slot>
    </div>
</template>

<script>

    export default {
    }
</script>

<style scoped>
    .quote {
        border: 1px solid darkgray;
        box-shadow: 1px 1px 2px darkgray;
        padding: 25px 20px;
        font-size: 24px;
        font-family: 'Arizonia', cursive;
        color: #6e6e6e;
        curser: pointer;
    }
    .quote:hover {
        background-color: #ffe2e2;
    }
</style>