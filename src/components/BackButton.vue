<template>
    <div class="back-button">
        <img src="/src/assets/back-icon.svg" alt="">
    </div>
</template>
<script setup></script>
<style scoped>
.back-button {
    display: flex;
    border-radius: 1.5rem;
    align-items: center;
    text-align: center;
    justify-content: center;
    width: fit-content;
    height: 3rem;
    background-color: #EDEBEE;
    column-gap: 0.7rem;
    padding-left: 0.85rem;
    padding-right: 0.85rem;
    position: absolute;
    top: 4rem;
    left: 1.25rem;
    z-index: 3;
}

.back-button:hover {
    cursor: pointer;
}
</style>