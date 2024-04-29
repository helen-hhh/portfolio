<template>
    <div class="main" @mouseup="down = false" @mousemove="slide">
        <div class="back-wrapper">
            <BackButton @click="$emit('close')"></BackButton>
        </div>
        <div class="left">
            <iframe src="https://player.vimeo.com/video/939547939?h=ee5dd7fdb0&autoplay=1&loop=1"
                style="width: 100%; height: 60%; position: absolute; top: 6rem; overflow: hidden; z-index: 1;"
                frameborder="0" allow="autoplay; fullscreen" allowfullscreen></iframe>
            <iframe src="https://player.vimeo.com/video/940512793?h=d5ccb2ba75&autoplay=1&loop=1"
                style="width: 100%; height: 100%; position: absolute; top: 43rem; overflow: hidden; z-index: 1;"
                frameborder="0" allow="autoplay; fullscreen" allowfullscreen></iframe>
            <div style="margin-top: 91rem; display: flex; border: dashed 1px black;">
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
                <div class="gap-context"
                    style="padding-bottom: 1rem; padding-right: 1rem; padding-top: 1rem; border-right: 1px dashed black;">
                    <h5>[ Context ]</h5>
                    <h3>"Invisible Women" draws attention to our unequal world that constantly lets women down and
                        doesn't
                        separate information by gender to take into account people's gender-specific needs and
                        characteristics. It shows the consequences of the fact that women have not had a seat at the
                        decision-making table for a long time </h3>
                    <p class="gap-project-descr">Why does Google Maps have the most environmentally friendly and fastest
                        route, but not the safest? Why are the streets cleared first in winter and then at some point
                        later, the footpaths, public transport tracks and cycle paths are cleared of snow? Why does the
                        Apple Watch slip on your wrist, but it sits like a perfect fit on your brother's? Why are women
                        much more likely to be severely injured in a car accident than men?
                        <br>
                        All of these products and systems are designed with a male-default mindset. Caroline Criado
                        Perez's illuminating book, "Invisible Women" sheds light on this phenomenon, revealing how
                        historical gender data gaps have systematically disadvantaged half of the population.
                    </p>
                    <h3 style="margin-top: 1rem;">What is a book and what can it be?</h3>
                    <p class="gap-project-descr">In the winter semester 2023/24, we dealt with the topic "The resistant
                        book - positions and perspectives on publishing and bookmaking". In this context, I asked myself
                        how a book can function in the digital space</p>
                </div>

                <div class="gap-filler" style="border-top: 1px dashed black;"></div>
                <div class="gap-problem">
                    <div>
                        <h5>[ Problem ]</h5>
                        <h3>How can I prepare a large amount of information in such a way that decision-makers can
                            easily find the information that is relevant to their work?</h3>
                        <p class="gap-project-descr">The book "Invisible Women" is the result of extensive research that
                            shows how women are disadvantaged in various design disciplines. This is supported by
                            numerous examples and statistics. With my semester project, I tried to restructure the
                            information so that designers can efficiently find the right data to make more informed
                            decisions.
                        </p>
                    </div>
                    <div class="gap-small-filler"></div>
                    <div class="gap-image-container">
                        <img style="height: 100%; width: 32%;" src="/src/assets/gap-obsidian.jpg" alt="">
                        <img style="height: 100%; width: 32%;" src="/src/assets/gap08.jpg" alt="">
                        <img style="height: 100%; width: 32%;" src="/src/assets/gap-code.jpg" alt="">
                    </div>
                    <p class="gap-project-descr"
                        style="margin-top: 0; padding-right: 1rem; padding-top: 1rem; padding-bottom: 1rem; border-right: dashed 1px black; border-bottom: dashed 1px black;">
                        During my
                        process, I
                        realized that the
                        analogue book might not be the
                        right format for that.
                        As it is such a quickly changing and broad topic, I needed something expandable which is why
                        I decided to design and implement an e-book.</p>
                </div>
                <div class="gap-filler"></div>
                <div class="gap-solution"
                    style="padding-bottom: 1rem; padding-right: 1rem; border-bottom: dashed 1px black; border-right: dashed 1px black;">
                    <h5>[ Solution ]</h5>
                    <h3>I tried to translate the functionalities, use
                        and handling of an analog book into digital, but also added the possibilities that the
                        interactive offers.</h3>
                    <p class="gap-project-descr">
                        You can seamlessly navigate between chapters, mark your favorite pages, add personal
                        annotations, and read existing, supplementary notes, enhancing the reading experience and
                        simplifying the search for specific information.
                        <br>
                        Visual elements of the e-book are based on statistics, scientific data analysis and diagrams as
                        well as overlays. This is intended to make it clear that information is not necessarily missing,
                        but simply needs to be included in the data sets. Everything is already there. You just have to
                        make the effort to make it visible and read it.
                    </p>
                </div>
                <div class="gap-filler"></div>
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
import CategoryProject from '../components/CategoryProject.vue';
import BackButton from '../components/BackButton.vue';

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
    font-size: 0.9rem;
    font-weight: 400;
    cursor: pointer;
}

.right::-webkit-scrollbar {
    display: none;
}

.right {
    -ms-overflow-style: none;
    /* IE and Edge */
    scrollbar-width: none;
    /* Firefox */
}

.left::-webkit-scrollbar {
    display: none;
}

.left {
    -ms-overflow-style: none;
    /* IE and Edge */
    scrollbar-width: none;
    /* Firefox */
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
    position: relative;
}

.right {
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

.categories {
    display: flex;
    column-gap: 1rem;
    align-items: center;
    justify-content: center;
    margin-top: 13rem;
}

.table-container {
    margin: 3rem 3rem 0 3rem;
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
    font-size: 1.1rem;
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
    font-size: 0.9rem;
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