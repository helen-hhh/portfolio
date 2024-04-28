<template>
    <div class="coding-main" @mouseup="down = false" @mousemove="slide">
        <div class="coding-back-wrapper">
            <BackButton @click="$emit('close')"></BackButton>
        </div>
        <div class="coding-left">
            <iframe
                src="https://player.vimeo.com/video/940161975?&autoplay=1&loop=1&badge=0&amp;autopause=0&amp;player_id=0&amp;app_id=58479"
                style="width: 100%; height: 60%; position: absolute; top: 6rem; overflow: hidden; z-index: 1;"
                frameborder="0" allow="autoplay; fullscreen" allowfullscreen></iframe>
            <iframe src="https://player.vimeo.com/video/940217732?h=41f8777102&autoplay=1&loop=1"
                style="width: 100%; height: 60%; position: absolute; top: 45rem; overflow: hidden; z-index: 1; padding-bottom: 6rem;"
                frameborder="0" allow="autoplay; fullscreen" allowfullscreen></iframe>
        </div>
        <div class="coding-right">
            <h1>Creative Coding</h1>
            <h1 class="h1-pixel">Sketches</h1>
            <h4 style="margin-top: 1rem;">Selection of creative coding projects made with p5.js</h4>
            <div class="coding-categories">
                <CategoryProject title="Dev"></CategoryProject>
                <CategoryProject title="Creative"></CategoryProject>
            </div>
            <div class="coding-table-container">
                <div class="coding-grid-item">Tools</div>
                <div class="coding-grid-item">Team</div>
                <div class="coding-grid-item">Role</div>
                <div class="coding-grid-item">Time</div>
                <div class="coding-grid-item">VSCode, p5.js</div>
                <div class="coding-grid-item">Just me</div>
                <div class="coding-grid-item">Concept, Creative Coding, Illustration</div>
                <div class="coding-grid-item">1 week each</div>
            </div>
            <div class="coding-content">
                <div class="coding-filler"></div>
                <div class="coding-concept"
                    style="padding-bottom: 1rem; border-right: 1px dashed black; border-bottom: 1px dashed black;">
                    <h5>[ Smile ] [ Underwater Illustration ]</h5>
                    <h3>How it started</h3>
                    <p class="coding-project-descr">Since 2022, I've been experimenting and playing around with HTML,
                        CSS, and particularly p5.js. Here are two sketches from the beginning of my coding journey.
                    </p>
                </div>
            </div>


        </div>
        <div @mousedown="down = true" class="coding-slider-button">
            <img class="coding-slider-icon" src="/src/assets/slider-icon.svg" alt="">
        </div>
    </div>
</template>

<script setup lang="ts">

import { ref } from 'vue'
import CategoryProject from '@/components/CategoryProject.vue';
import BackButton from '@/components/BackButton.vue';

let down = ref(false);
let xPos = ref("50vw");

function slide(e: MouseEvent) {
    if (down.value) {
        xPos.value = e.clientX + 'px';
        document.body.style.cursor = 'grabbing'
    }

    else {
        // Setze den Cursor zurück, wenn die Bedingung nicht erfüllt ist
        document.body.style.cursor = '';

    }
}
</script>

<style>
.coding-main {
    display: flex;
    position: absolute;
    top: 0;
    left: 0;
    width: 100vw;
    user-select: none;
    -webkit-user-select: none;
    z-index: 3;
}

.coding-back-wrapper:hover .back-button:after {
    content: 'Back';
    font-family: 'Helvetica Neue, Arial';
    font-size: 0.9rem;
    font-weight: 400;
    cursor: pointer;
}

.coding-left {
    background-color: rgba(198, 205, 216, 0.7);
    width: v-bind(xPos);
    min-width: 20vw;
    max-width: 60vw;
    height: 100vh;
    overflow-y: scroll;
    display: flex;
    flex-direction: column;
    gap: 0;
    text-align: center;
    align-items: center;
    position: relative;
}

.coding-left::-webkit-scrollbar {
    display: none;
}

.coding-right {
    display: flex;
    flex-direction: column;
    text-align: center;
    padding-top: 7rem;
    width: calc(100vw - v-bind(xPos));
    background-color: #D9D9D9;
    height: calc(100vh - 7rem);
    overflow-y: scroll;
    min-width: 40vw;
    max-width: 80vw;
}

.coding-right::-webkit-scrollbar {
    display: none;
}

.coding-categories {
    display: flex;
    column-gap: 1rem;
    align-items: center;
    justify-content: center;
    padding: 13rem 0 3rem 0;
    margin: 0 3rem 0 3rem;
    border-right: 1px dashed black;
}

.coding-table-container {
    margin: 0 3rem 0 3rem;
    display: grid;
    grid-template-columns: auto auto auto auto;
    gap: 0px;
    border: solid 0.5px;
}

.coding-filler {
    height: 4rem;
    width: 100%;
    border-left: 1px dashed black;
}

.coding-small-filler {
    height: 1rem;
    width: 100%;
    border-left: 1px dashed black;
}

.coding-project-descr {
    font-size: 1.1rem;
    line-height: inherit;
    margin-top: 1rem;
    margin-right: 1rem;
}

.coding-content {
    text-align: left;
    padding: 3rem;
    padding-top: 0;
}

.coding-image-container {
    width: calc(100% - 2rem);
    padding: 1rem;
    border: dashed 1px black;
}

.coding-grid-item {
    padding: 2rem;
    border: 0.5px solid;
    justify-content: center;
    text-align: center;
    align-items: center;
    display: flex;
    font-family: 'Helvetica Neue, Arial';
    font-size: 0.9rem;
    font-weight: 400;
    margin: 0;
}

.coding-slider-button {
    position: absolute;
    left: clamp(calc(20vw - 1.5rem), calc(v-bind(xPos) - 1.5rem), calc(60vw - 1.5rem));
    top: 50vh;
    width: 3rem;
    height: 3rem;
    border-radius: 1.5rem;
    background-color: #EDEBEE;
    display: flex;
    text-align: center;
    align-items: center;
    justify-content: center;
}

.coding-slider-button:hover {
    cursor: grab;
}

.coding-slider-icon {
    width: 1.3rem;
    height: 1.3rem;
    pointer-events: none;
}
</style>