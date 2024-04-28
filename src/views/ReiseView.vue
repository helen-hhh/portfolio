<template>
    <div class="reise-main" @mouseup="down = false" @mousemove="slide">
        <div class="reise-back-wrapper">
            <BackButton @click="$emit('close')"></BackButton>
        </div>
        <div class="reise-left">
            <iframe src="https://player.vimeo.com/video/940348814?h=86293f99e0&autoplay=1&loop=1"
                style="width: 100%; height: 60%; position: absolute; top: 6rem; overflow: hidden; z-index: 1;"
                frameborder="0" allow="autoplay; fullscreen" allowfullscreen></iframe>
            <div style="display: flex; border: dashed 1px black; margin-top: 45rem;">
                <img style="width: 50%;" src="/src/assets/reise02.jpg" alt="">
                <img style="width: 50%; border-left: dashed 1px black;" src="/src/assets/reise-gif.gif" alt="">
            </div>
            <div style="display: flex; align-items: center; border: dashed 1px black; border-top: 0;">
                <img style="width: 50%; border-right: dashed 1px black;" src="/src/assets/reise01.jpg" alt="">
                <img style="width: 50%;" src="/src/assets/reise04.jpg" alt="">
            </div>
        </div>
        <div class="reise-right">
            <h1>Reise ans</h1>
            <h1 class="h1-pixel">Ende des Bettes</h1>
            <h4 style="margin-top: 1rem;">A translation of a text into a publication and a website</h4>
            <div class="reise-categories">
                <CategoryProject title="Typo"></CategoryProject>
                <CategoryProject title="Edit"></CategoryProject>
                <CategoryProject title="Dev"></CategoryProject>
            </div>
            <div class="reise-table-container">
                <div class="reise-grid-item">Tools</div>
                <div class="reise-grid-item">Team</div>
                <div class="reise-grid-item">Role</div>
                <div class="reise-grid-item">Time</div>
                <div class="reise-grid-item">HTML, CSS, JavaScript, InDesign</div>
                <div class="reise-grid-item">Just me</div>
                <div class="reise-grid-item">Concept, Editorial Design, Development</div>
                <div class="reise-grid-item">2 weeks</div>
            </div>
            <div class="reise-content">
                <div class="reise-filler"></div>
                <div class="reise-concept"
                    style="padding-bottom: 1rem; border-right: 1px dashed black; border-bottom: 1px dashed black;">
                    <h5>[ Publication ]</h5>
                    <p class="reise-project-descr">In a two-week typography course, we explored the typographic
                        translation of content with different design strategies from editorial, micro- and
                        macrotypographical perspectives. In the first week our project involved creating a brochure that
                        typographically translates and reinterprets an extract from Paul B. Preciados book »Ein
                        Apartment auf dem Uranus – Chroniken eines Übergangs«.
                    </p>
                </div>
                <div class="reise-filler" style="border-top: 1px dashed black;"></div>
                <div class="reise-font"
                    style="border-bottom: dashed 1px black; border-right: dashed 1px black; padding-bottom: 1rem;">
                    <div>
                        <h5>[ Website ]</h5>
                        <p class="print-project-descr">In the second week of the typography basic course, I translated
                            the extract from Paul B. Preciados book »Ein Apartment auf dem Uranus – Chroniken eines
                            Übergangs« into a website I coded with HTML, CSS and JavaScript.

                            The words run over the screen constantly, and can only be stopped briefly, not reversed.
                        </p>
                    </div>
                </div>

            </div>


        </div>
        <div @mousedown="down = true" class="reise-slider-button">
            <img class="reise-slider-icon" src="/src/assets/slider-icon.svg" alt="">
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
.reise-main {
    display: flex;
    position: absolute;
    top: 0;
    left: 0;
    width: 100vw;
    user-select: none;
    -webkit-user-select: none;
    z-index: 3;
}

.reise-back-wrapper:hover .back-button:after {
    content: 'Back';
    font-family: 'Helvetica Neue, Arial';
    font-size: 0.9rem;
    font-weight: 400;
    cursor: pointer;
}

.reise-left {
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

.reise-left::-webkit-scrollbar {
    display: none;
}

.reise-right {
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

.reise-right::-webkit-scrollbar {
    display: none;
}

.reise-categories {
    display: flex;
    column-gap: 1rem;
    align-items: center;
    justify-content: center;
    padding: 13rem 0 3rem 0;
    margin: 0 3rem 0 3rem;
    border-right: 1px dashed black;
}

.reise-table-container {
    margin: 0 3rem 0 3rem;
    display: grid;
    grid-template-columns: auto auto auto auto;
    gap: 0px;
    border: solid 0.5px;
}

.reise-filler {
    height: 4rem;
    width: 100%;
    border-left: 1px dashed black;
}

.reise-small-filler {
    height: 1rem;
    width: 100%;
    border-left: 1px dashed black;
}

.reise-project-descr {
    font-size: 1.1rem;
    line-height: inherit;
    margin-top: 1rem;
    margin-right: 1rem;
}

.reise-content {
    text-align: left;
    padding: 3rem;
    padding-top: 0;
}

.reise-image-container {
    width: calc(100% - 2rem);
    padding: 1rem;
    border: dashed 1px black;
}

.reise-grid-item {
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

.reise-slider-button {
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

.reise-slider-button:hover {
    cursor: grab;
}

.reise-slider-icon {
    width: 1.3rem;
    height: 1.3rem;
    pointer-events: none;
}
</style>