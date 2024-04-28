<template>
    <div class="print-main" @mouseup="down = false" @mousemove="slide">
        <div class="print-back-wrapper">
            <BackButton @click="$emit('close')"></BackButton>
        </div>
        <div class="print-left">
            <img src="/src/assets/print-buchmesse.gif" style="width: 60%; margin-top: 8rem; margin-bottom: 8rem;"
                alt="">
            <img src="/src/assets/print-04.png" style="width: 100%;" alt="">
            <img src="/src/assets/print-03.png" style="width: 80%; margin-top: 8rem; margin-bottom: 8rem;" alt="">
        </div>
        <div class="print-right">
            <h1>Print Media -</h1>
            <h1 class="h1-pixel">a selection</h1>
            <h4 style="margin-top: 1rem;">Selection of posters, postcards and other print media</h4>
            <div class="print-categories">
                <CategoryProject title="Typo"></CategoryProject>
                <CategoryProject title="Edit"></CategoryProject>
                <CategoryProject title="Graphic"></CategoryProject>
            </div>
            <div class="print-table-container">
                <div class="print-grid-item">Tools</div>
                <div class="print-grid-item">Team</div>
                <div class="print-grid-item">Role</div>
                <div class="print-grid-item">Time</div>
                <div class="print-grid-item">InDesign, Figma</div>
                <div class="print-grid-item">Various</div>
                <div class="print-grid-item">Research, Creative Coding, Font Sketch, Editorial Design</div>
                <div class="print-grid-item">2023-24</div>
            </div>
            <div class="print-content">
                <div class="print-filler"></div>
                <div class="print-concept" style="padding-bottom: 1rem; border-right: 1px dashed black;">
                    <h5>[ Project 1 ]</h5>
                    <h3>Invitation Postcards for Burg Giebichenstein's booth at Leipzig Book Fair</h3>
                    <p class="print-project-descr">In developing the design concept, we dealt with the questions of what
                        a book is, what it can be and which materials and tools are actually used so that the finished
                        book can be shown and sold at the book fair. To do this, we compiled an incomplete list, which I
                        then set typographically, and collected materials that are used in bookbinding or printing and
                        scanned them.
                        <br>
                        <em>Background images in collaboration with Mona Ortner</em>
                    </p>
                </div>
                <div class="print-filler" style="border-top: 1px dashed black;"></div>
                <div class="print-font"
                    style="border-bottom: dashed 1px black; border-right: dashed 1px black; padding-bottom: 1rem;">
                    <div>
                        <h5>[ Project 2 ]</h5>
                        <h3>Sexism in AI</h3>
                        <p class="print-project-descr">During a theory compact week, we discussed the critical issue of
                            biases embedded in algorithms, which manifests itself particularly in scenarios such
                            as job application processes, where they can (unintentionally) disadvantage people perceived
                            as female. As part of this, we created the flyer with our own texts that resulted
                            from our research on the topic of sexism in artificial intelligence.
                            <br><em>Project together with Liv Burhenne, Klara Kapprell and Sofia Prinz, Design by
                                me</em>
                        </p>
                    </div>
                </div>
                <div class="print-filler"></div>
                <div class="print-visuals">
                    <h5>[ Project 3 ]</h5>
                    <h3>Composition as explanation</h3>
                    <p class="print-project-descr">A poster I made about world building in design featuring a poem
                        written by ChatGPT. This project was created in the visual
                        design basics week as part of my studies.</p>
                </div>
            </div>


        </div>
        <div @mousedown="down = true" class="print-slider-button">
            <img class="print-slider-icon" src="/src/assets/slider-icon.svg" alt="">
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
.print-main {
    display: flex;
    position: absolute;
    top: 0;
    left: 0;
    width: 100vw;
    user-select: none;
    -webkit-user-select: none;
    z-index: 3;
}

.print-back-wrapper:hover .back-button:after {
    content: 'Back';
    font-family: 'Helvetica Neue';
    font-size: 0.9rem;
    font-weight: 400;
    cursor: pointer;
}

.print-left {
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

.print-left::-webkit-scrollbar {
    display: none;
}

.print-left {
    -ms-overflow-style: none;
    /* IE and Edge */
    scrollbar-width: none;
    /* Firefox */
}

.print-right {
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

.print-right::-webkit-scrollbar {
    display: none;
}

.print-right {
    -ms-overflow-style: none;
    /* IE and Edge */
    scrollbar-width: none;
    /* Firefox */
}

.print-categories {
    display: flex;
    column-gap: 1rem;
    align-items: center;
    justify-content: center;
    padding: 13rem 0 3rem 0;
    margin: 0 3rem 0 3rem;
    border-right: 1px dashed black;
}

.print-table-container {
    margin: 0 3rem 0 3rem;
    display: grid;
    grid-template-columns: auto auto auto auto;
    gap: 0px;
    border: solid 0.5px;
}

.print-filler {
    height: 4rem;
    width: 100%;
    border-left: 1px dashed black;
}

.print-small-filler {
    height: 1rem;
    width: 100%;
    border-left: 1px dashed black;
}

.print-project-descr {
    font-size: 1.1rem;
    line-height: inherit;
    margin-top: 1rem;
    margin-right: 1rem;
}

.print-content {
    text-align: left;
    padding: 3rem;
    padding-top: 0;
}

.print-image-container {
    width: calc(100% - 2rem);
    padding: 1rem;
    border: dashed 1px black;
}

.print-grid-item {
    padding: 2rem;
    border: 0.5px solid;
    justify-content: center;
    text-align: center;
    align-items: center;
    display: flex;
    font-family: 'Helvetica Neue';
    font-size: 0.9rem;
    font-weight: 400;
    margin: 0;
}

.print-slider-button {
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

.print-slider-button:hover {
    cursor: grab;
}

.print-slider-icon {
    width: 1.3rem;
    height: 1.3rem;
    pointer-events: none;
}
</style>