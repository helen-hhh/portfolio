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
                <div class="print-concept" style="margin-bottom: 8rem;">
                    <h3 class="category-font">Context</h3>
                    <h3>History books often overlook the everyday lives of marginalized groups, focusing on a few
                        privileged</h3>
                    <p class="print-project-descr">In school we learned a lot about kings, battles and the power
                        struggles
                        of the upper class. Often
                        forgotten are the stories of marginalized groups and their everyday lives.
                        To counteract this, we delved into Untold Stories - Missing Biographies in the Type and
                        Typography module with Prof. Andrea Tinnes and Teresa Schönherr. </p>
                </div>
                <h3 class="category-font">Font</h3>
                <div class="print-font"
                    style="display: flex; flex-direction: row; align-items: start; gap: 2rem; margin-bottom: 8rem;">
                    <div>

                        <h3>I wrote about print Lovelace - the pioneer of programming</h3>
                        <p class="print-project-descr">The predecessor of our computer - the analytical engine - was
                            supposed
                            to receive its commands,
                            which print Lovelace wrote, via punch cards. That is why I decided to work with circles as
                            the
                            main graphic element.
                            We were asked to create a typeface that conveys the character of our person. I used a grid
                            of
                            5x5 circles and connected some of the circles in order to improve legibility and to support
                            the
                            mechanical character.</p>
                    </div>
                </div>
                <div class="print-visuals">
                    <h3 class="category-font">Visual Concept</h3>
                    <h3>"We may say most aptly that the Analytical Engine weaves algebraic patterns just as the
                        Jacquard-loom weaves flowers and leaves."</h3>
                    <div style="display: flex; flex-direction: row; column-gap: 2rem; margin-top: 2rem;">
                        <p class="print-project-descr" style="margin-top: 0;">To get to the heart of her oeuvre and work
                            with what she did the
                            important groundwork for -
                            programming - I wanted to use code myself. After many experiments, the following was created
                            in p5.js:
                            The circle walks across the screen randomly and leave a pattern that resembles a wool
                            structure - just like the material used by the Jacquard loom - the machine Charles Babbage
                            was inspired by to use punch cards for his own Analytical Engine.</p>
                    </div>
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
    font-size: 1rem;
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

.print-right {
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

.print-right::-webkit-scrollbar {
    display: none;
}

.print-categories {
    display: flex;
    column-gap: 1rem;
    align-items: center;
    justify-content: center;
    margin-top: 18rem;
}

.print-table-container {
    margin: 3rem 3rem 1rem 3rem;
    display: grid;
    grid-template-columns: auto auto auto auto;
    gap: 0px;
    border: solid 0.5px;
}

.print-project-descr {
    font-size: 1.3rem;
    line-height: inherit;
    margin-top: 2rem;
}

.print-content {
    text-align: left;
    padding: 3rem;
}

.print-grid-item {
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