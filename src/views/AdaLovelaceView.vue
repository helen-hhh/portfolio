<template>
    <div class="ada-main" @mouseup="down = false" @mousemove="slide">
        <div class="ada-back-wrapper">
            <BackButton @click="$emit('close')"></BackButton>
        </div>
        <div class="ada-left">
            <img src="/src/assets/untold0053-min.jpg" style="width: 100%;" alt="">
            <img src="/src/assets/untold0054-min.jpg" style="width: 100%;" alt="">
            <img src="/src/assets/ada-blättern.gif" style="width: 60%; margin-top: 8rem; margin-bottom: 8rem;" alt="">
            <img src="/src/assets/untold0055-min.jpg" style="width: 100%;" alt="">
        </div>
        <div class="ada-right">
            <h1>Untold Stories</h1>
            <h1 class="h1-pixel">Ada Lovelace</h1>
            <h4 style="margin-top: 1rem;">An editorial design and font sketch about Ada Lovelace</h4>
            <div class="ada-categories">
                <CategoryProject title="Edit"></CategoryProject>
                <CategoryProject title="Creative"></CategoryProject>
                <CategoryProject title="Typo"></CategoryProject>
            </div>
            <div class="ada-table-container">
                <div class="ada-grid-item">Tools</div>
                <div class="ada-grid-item">Team</div>
                <div class="ada-grid-item">Role</div>
                <div class="ada-grid-item">Time</div>
                <div class="ada-grid-item">p5.js, Glyphs, InDesign, Illustrator</div>
                <div class="ada-grid-item">Just me</div>
                <div class="ada-grid-item">Research, Creative Coding, Font Sketch, Editorial Design</div>
                <div class="ada-grid-item">4 weeks</div>
            </div>
            <div class="ada-content">
                <div class="ada-filler"></div>
                <div class="ada-concept" style="padding-bottom: 1rem; border-right: 1px dashed black;">
                    <h5>[ Context ]</h5>
                    <h3>History books often overlook the everyday lives of marginalized groups, focusing on a few
                        privileged</h3>
                    <p class="ada-project-descr">In school we learned a lot about kings, battles and the power struggles
                        of the upper class. Often
                        forgotten are the stories of marginalized groups and their everyday lives.
                        To counteract this, we delved into Untold Stories - Missing Biographies in the Type and
                        Typography module with Prof. Andrea Tinnes and Teresa Schönherr. </p>
                </div>
                <div class="ada-filler" style="border-top: 1px dashed black;"></div>
                <div class="ada-font">
                    <div>
                        <h5>[ Font ]</h5>
                        <h3>I wrote about Ada Lovelace - the pioneer of programming</h3>
                        <p class="ada-project-descr">The predecessor of our computer - the analytical engine - was
                            supposed
                            to receive its commands,
                            which Ada Lovelace wrote, via punch cards. That is why I decided to work with circles as the
                            main graphic element.
                            We were asked to create a typeface that conveys the character of our person. I used a grid
                            of
                            5x5 circles and connected some of the circles in order to improve legibility and to support
                            the
                            mechanical character.</p>
                    </div>
                    <div class="ada-small-filler"></div>
                    <div class="ada-image-container">
                        <img src="/src/assets/ada-font.gif" style="width: 50%; height: auto;" alt="">
                    </div>
                </div>
                <div class="ada-filler"></div>
                <div class="ada-visuals">
                    <h5>[ Visual Concept ]</h5>
                    <h3>"We may say most aptly that the Analytical Engine weaves algebraic patterns just as the
                        Jacquard-loom weaves flowers and leaves."</h3>
                    <p class="ada-project-descr">To get to the heart of her oeuvre and work
                        with what she did the
                        important groundwork for -
                        programming - I wanted to use code myself. After many experiments, the following was created
                        in p5.js:
                        The circle walks across the screen randomly and leave a pattern that resembles a wool
                        structure - just like the material used by the Jacquard loom - the machine Charles Babbage
                        was inspired by to use punch cards for his own Analytical Engine.</p>
                    <div class="ada-small-filler"></div>
                    <div class="ada-image-container">
                        <img src="/src/assets/ada-poster.gif" style="width: 50%;" alt="">
                    </div>
                </div>
            </div>


        </div>
        <div @mousedown="down = true" class="ada-slider-button">
            <img class="ada-slider-icon" src="/src/assets/slider-icon.svg" alt="">
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
.ada-main {
    display: flex;
    position: absolute;
    top: 0;
    left: 0;
    width: 100vw;
    user-select: none;
    -webkit-user-select: none;
    z-index: 3;
}

.ada-back-wrapper:hover .back-button:after {
    content: 'Back';
    font-family: 'Helvetica Neue';
    font-size: 0.9rem;
    font-weight: 400;
    cursor: pointer;
}

.ada-left {
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

.ada-left::-webkit-scrollbar {
    display: none;
}

.ada-left {
    -ms-overflow-style: none;
    /* IE and Edge */
    scrollbar-width: none;
    /* Firefox */
}

.ada-right {
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

.ada-right::-webkit-scrollbar {
    display: none;
}

.ada-right {
    -ms-overflow-style: none;
    /* IE and Edge */
    scrollbar-width: none;
    /* Firefox */
}

.ada-categories {
    display: flex;
    column-gap: 1rem;
    align-items: center;
    justify-content: center;
    padding: 13rem 0 3rem 0;
    margin: 0 3rem 0 3rem;
    border-right: 1px dashed black;
}

.ada-table-container {
    margin: 0 3rem 0 3rem;
    display: grid;
    grid-template-columns: auto auto auto auto;
    gap: 0px;
    border: solid 0.5px;
}

.ada-filler {
    height: 4rem;
    width: 100%;
    border-left: 1px dashed black;
}

.ada-small-filler {
    height: 1rem;
    width: 100%;
    border-left: 1px dashed black;
}

.ada-project-descr {
    font-size: 1.1rem;
    line-height: inherit;
    margin-top: 1rem;
}

.ada-content {
    text-align: left;
    padding: 3rem;
    padding-top: 0;
}

.ada-image-container {
    width: calc(100% - 2rem);
    padding: 1rem;
    border: dashed 1px black;
}

.ada-grid-item {
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

.ada-slider-button {
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

.ada-slider-button:hover {
    cursor: grab;
}

.ada-slider-icon {
    width: 1.3rem;
    height: 1.3rem;
    pointer-events: none;
}
</style>