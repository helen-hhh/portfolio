<template>
    <div class="category-div">
        <p>{{ title }}</p>
    </div>
</template>

<script setup>
import { defineProps, computed } from 'vue';

const props = defineProps({
    title: String,
});

const title = computed(() => {
    switch (props.title) {
        case 'Dev':
            return "Development";
        case 'UX':
            return "UX/UI Design";
        case 'Typo':
            return "Typography";
        case 'Web':
            return "Webdesign";
        case 'Edit':
            return "Editorial Design";
        case 'Research':
            return "UX Research";
        case 'Illu':
            return "Illustration";
        case 'Graphic':
            return "Graphic Design";
        case 'Creative':
            return "Creative Coding";
        default:
            return props.title;
    }
});
</script>

<style scoped>
.category-div {
    padding: 0.9rem 1.8rem 0.9rem 1.8rem;
    border-radius: 1.5rem;
    display: inline-block;
    background-color: #D4E2FC;
}
</style>