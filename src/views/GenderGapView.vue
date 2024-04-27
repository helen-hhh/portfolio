<template>
    <div class="main" @mouseup="down = false" @mousemove="slide">
        <div class="back-wrapper">
            <BackButton @click="$emit('close')"></BackButton>
        </div>
        <div class="left">
            <img src="/src/assets/gap-placeholder.jpg" style="width: 40%; margin: 6rem;" alt="">
            <img src="/src/assets/gap-placeholder02.jpg" style="width: 100%;" alt="">
            <div style="display: flex; border: dashed 1px black;">
                <img style="width: 50%;" src="/src/assets/gap03.png" alt="">
                <img style="width: 50%; border-left: dashed 1px black;" src="/src/assets/gap04.jpg" alt="">
            </div>
            <div style="display: flex; align-items: center; border: dashed 1px black; border-top: 0;">
                <img style="width: 50%; border-right: dashed 1px black;" src="/src/assets/gap07.jpg" alt="">
                <img style="width: 40%; height: auto; padding: 5%;" src="/src/assets/gap09.png" alt="">
            </div>
            <img src="/src/assets/gap05.jpg" style="width: 100%;" alt="">
        </div>
        <div class="right">
            <h1>Gender Data Gap</h1>
            <h1 class="h1-pixel">(in Design)</h1>
            <h4 style="margin-top: 1rem;">A translation of a book into the digital</h4>
            <div class="categories">
                <CategoryProject title="Dev"></CategoryProject>
                <CategoryProject title="Web"></CategoryProject>
                <CategoryProject title="Typo"></CategoryProject>
            </div>
            <div class="table-container">
                <div class="grid-item">Tools</div>
                <div class="grid-item">Team</div>
                <div class="grid-item">Role</div>
                <div class="grid-item">Time</div>
                <div class="grid-item">VSCode, Figma, Obsidian</div>
                <div class="grid-item">Just me</div>
                <div class="grid-item">Research, Development, Prototyping, Design, Concept</div>
                <div class="grid-item">4 months</div>
            </div>
            <div class="gap-filler"></div>
            <div class="content">
                <div class="gap-context" style="padding-bottom: 1rem; border-right: 1px dashed black;">
                    <h5>[ Context ]</h5>
                    <h3></h3>
                    <p class="gap-project-descr"></p>
                </div>

                <div class="gap-filler" style="border-top: 1px dashed black;"></div>
                <div class="gap-problem">
                    <div>
                        <h5>[ Problem ]</h5>
                        <h3></h3>
                        <p class="gap-project-descr"></p>
                    </div>
                    <div class="gap-small-filler"></div>
                    <div class="gap-image-container">
                        <img style="height: 100%; width: 32%;" src="/src/assets/gap-obsidian.jpg" alt="">
                        <img style="height: 100%; width: 32%;" src="/src/assets/gap08.jpg" alt="">
                        <img style="height: 100%; width: 32%;" src="/src/assets/gap-code.jpg" alt="">
                    </div>
                </div>
                <div class="gap-filler"></div>
                <div class="gap-solution">
                    <h5>[ Solution ]</h5>
                    <h3></h3>
                    <p class="gap-project-descr"></p>
                    <div class="gap-small-filler"></div>
                    <div class="gap-image-container">
                        <img src="" style="width: 50%;" alt="">
                    </div>
                </div>
                <div class="gap-learnings">
                    <h5>[ Learnings ]</h5>
                    <h3>Research is key</h3>
                    <p class="gap-project-descr">The project made me all the more aware how important testing with
                        diverse perspectives is in all stages of the design process, in order to identify design flaws
                        and biases that may otherwise remain concealed.</p>
                </div>
            </div>
        </div>
    </div>

    <div @mousedown="down = true" class="slider-button">
        <img class="slider-icon" src="/src/assets/slider-icon.svg" alt="">
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
.main {
    display: flex;
    position: absolute;
    top: 0;
    left: 0;
    width: 100vw;
    user-select: none;
    -webkit-user-select: none;
    z-index: 3;
}

.back-wrapper:hover .back-button:after {
    content: 'Back';
    font-family: 'Helvetica Neue';
    font-size: 1rem;
    font-weight: 400;
    cursor: pointer;
}

.right::-webkit-scrollbar {
    display: none;
}

.left::-webkit-scrollbar {
    display: none;
}

.left {
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
}

.right {
    display: flex;
    flex-direction: column;
    text-align: center;
    padding-top: 10rem;
    width: calc(100vw - v-bind(xPos));
    background-color: #D9D9D9;
    height: calc(100vh - 10rem);
    overflow-y: scroll;
    min-width: 40vw;
    max-width: 80vw;

}

.categories {
    display: flex;
    column-gap: 1rem;
    align-items: center;
    justify-content: center;
    margin-top: 18rem;
}

.table-container {
    margin: 3rem 3rem 1rem 3rem;
    display: grid;
    grid-template-columns: auto auto auto auto;
    gap: 0px;
    border: solid 0.5px;
}

.gap-filler {
    height: 4rem;
    width: 100%;
    border-left: 1px dashed black;
}

.gap-small-filler {
    height: 1rem;
    width: 100%;
    border-left: 1px dashed black;
}

.gap-project-descr {
    font-size: 1.3rem;
    line-height: inherit;
    margin-top: 1rem;
}

.content {
    text-align: left;
    padding: 3rem;
    padding-top: 0;
}

.gap-image-container {
    width: calc(100% - 2rem);
    padding: 1rem;
    border: dashed 1px black;
    display: flex;
    flex-direction: row;
    column-gap: 1rem;
}

.grid-item {
    padding: 2rem;
    border: 0.5px solid;
    justify-content: center;
    text-align: center;
    align-items: center;
    display: flex;
    font-family: 'Helvetica Neue';
    font-size: 1rem;
    font-weight: 400;
    margin: 0;
}

.slider-button {
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
    z-index: 5;
}

.slider-button:hover {
    cursor: grab;
}

.slider-icon {
    width: 1.3rem;
    height: 1.3rem;
    pointer-events: none;
}
</style>