<template>
    <div class="museum-main" @mouseup="down = false" @mousemove="slide">
        <div class="museum-back-wrapper">
            <BackButton @click="$emit('close')"></BackButton>
        </div>
        <div class="museum-left">
            <iframe src="https://player.vimeo.com/video/940520322?h=17afa82cf8&autoplay=1&loop=1"
                style="width: 100%; height: 60%; position: absolute; top: 6rem; overflow: hidden; z-index: 1;"
                frameborder="0" allow="autoplay; fullscreen" allowfullscreen></iframe>
            <div style="margin-top: 45rem; display: flex; border: dashed 1px black;">
                <img style="width: 50%;" src="/src/assets/museum01.png" alt="">
                <img style="width: 50%; border-left: dashed 1px black;" src="/src/assets/museum02.png" alt="">
            </div>
            <div style="display: flex; align-items: center; border: dashed 1px black; border-top: 0;">
                <div style="width: 50%;"></div>
                <img style="width: 50%; border-left: dashed 1px black;" src="/src/assets/museum03.png" alt="">
            </div>
        </div>
        <div class="museum-right">
            <h1>Hidden Stories</h1>
            <h1 class="h1-pixel">Museum</h1>
            <h4 style="margin-top: 1rem;">An app for visitors to save and recall their favorite museum exhibits.</h4>
            <div class="museum-categories">
                <CategoryProject title="UX"></CategoryProject>
                <CategoryProject title="Research"></CategoryProject>
                <CategoryProject title="Illu"></CategoryProject>
            </div>
            <div class="museum-table-container">
                <div class="museum-grid-item">Tools</div>
                <div class="museum-grid-item">Team</div>
                <div class="museum-grid-item">Role</div>
                <div class="museum-grid-item">Time</div>
                <div class="museum-grid-item">Figma, Illustrator</div>
                <div class="museum-grid-item">Just me</div>
                <div class="museum-grid-item">UX Research, Visual Design, Illustrations, Prototyping, Usability Testing
                </div>
                <div class="museum-grid-item">6 months</div>
            </div>
            <div class="museum-content">
                <div class="museum-filler"></div>
                <div class="museum-concept" style="border-right: 1px dashed black;">
                    <h5>[ Summary ]</h5>
                    <h3></h3>
                    <p class="museum-project-descr">Whenever I leave a museum my phone gallery is cluttered with poorly
                        lit photos that I never find again when I need to recall it later. I found myself frustrated
                        with the limited ability to capture and recall my favorite exhibits. To address
                        this problem, I developed an app for the fictional Hidden Stories Museum, which allows users to
                        tailor their museum experience to their preferences and interests. This personalized app allows
                        users to capture and recall their favorite exhibits effortlessly, offering detailed information
                        about artworks and artists. With features tailored to individual preferences, such as exhibit
                        scanning and historical insights, the app aims to question how users engage with museum
                        collections and offers new ways.
                        <br>
                        This is a personal project I created independently.
                    </p>
                </div>
                <div class="museum-filler" style="border-top: 1px dashed black;"></div>
                <div class="museum-font">
                    <div>
                        <h5>[ Problem ]</h5>
                        <h3></h3>
                        <p class="museum-project-descr">Museum visitors are frustrated by long audio guides that cover
                            topics of little interest, a lack of interactivity and by the fact that there is no
                            possibility
                            to save
                            exhibitits. Additionally, for those with poor eyesight,
                            not being able to get close to the exhibits is a disadvantage. Museums should be a
                            democratic
                            space that stores and archives artwork over time for society to access. However, visitors
                            can only see a small curated fraction of the collection, and there is a desire for more
                            transparency and participation in what is presented.</p>
                    </div>
                </div>
                <div class="museum-filler"></div>
                <div class="museum-visuals">
                    <h5>[ Empathize ]</h5>
                    <h3>Secondary Research</h3>
                    <p class="museum-project-descr">At first I went to a few museums and
                        hahadve a look at their digital products that enhance the museum experience. I visited the MAK
                        Museum in Vienna, the SMK in Copenhagen, the MdbK in Leipzig as well as the SKD in Dresden.
                        Additionally, I read “The Future of the Museum - 28 Dialogues” by András Szántó to get into the
                        topic.</p>

                    <h3>User Interviews</h3>
                    <p class="museum-project-descr">During the museum visits, I talked to some employees to gain
                        insights about what they observed how people were going
                        through museums. After that, I interviewed people with different backgrounds to get a broad
                        spectrum of insights.</p>
                    <div class="museum-small-filler"></div>
                    <div class="museum-image-container">
                        <img src="/src/assets/user-interviews.png" style="width: 100%;" alt="">
                    </div>

                    <div style="border-right: dashed 1px black; border-bottom: dashed 1px black;">
                        <h3 style="padding-top: 1rem;">Pain Points</h3>
                        <p class="museum-project-descr" style="padding-bottom: 0;">Following an extensive process of
                            research,
                            I gathered and analyzed all
                            the information and identified the following pain points:
                        </p>
                        <ul>
                            <li>there is no easy way yet to save artworks or components of it to access later
                            </li>
                            <li>bad eyesight causes people to not be able to see the details anymore</li>
                            <li>often there is just one audioguide for all, but everyone has different interests, so
                                they
                                are
                                easily bored</li>
                        </ul>
                    </div>
                </div>
                <div class="museum-filler"></div>
                <div class="museum-visuals">
                    <h5>[ Define ]</h5>
                    <h3>List of Features</h3>
                    <p class="museum-project-descr" style="padding-bottom: 0;">Using the insights of my research, I
                        created a list of the
                        following features that aim to address these issues:</p>
                    <ul>
                        <li>Zoom Function</li>
                        <li>Scan Function that allows users to interact with the scanned artwork</li>
                        <li>Audioguide and Quiz tours that are customizable</li>
                        <li>Digital Archive with which users have the ability to vote for artifacts they want to see
                            displayed in upcoming exhibitions</li>
                        <li>Learning Section with articles, quizzes, games and more</li>
                    </ul>
                    <h3>User Flow</h3>
                    <div class="museum-small-filler"></div>
                    <div class="museum-image-container">
                        <img src="/src/assets/user-flow.png" style="width: 100%; height: auto;" alt="">
                    </div>
                </div>


                <div class="museum-filler"></div>
                <div class="museum-visuals">
                    <h5>[ Lo-Fi Prototype ]</h5>
                    <h3 style="margin-bottom: 1rem;">Key Insights of the Usability Study</h3>
                    <div class="museum-image-container">
                        <img src="/src/assets/lofi.png" style="width: 100%;" alt="">
                    </div>
                    <p class="museum-project-descr">Once the first version of the low-fidelity prototype in Figma was
                        complete, I
                        conducted a usability study
                        to test its design. Below, you can find the insights I acquired through the study.</p>
                    <div class="museum-small-filler"></div>
                    <div class="museum-image-container">
                        <img src="/src/assets/insights.png" style="width: 100%;" alt="">
                    </div>
                </div>

                <div class="museum-filler"></div>
                <div class="museum-visuals">
                    <h5>[ Hi-Fi Prototype ]</h5>
                    <h3>Design System</h3>
                    <div class="museum-small-filler"></div>
                    <div class="museum-image-container">
                        <img src="/src/assets/design-system.png" style="width: 100%;" alt="">
                    </div>
                    <h3 style="margin-top: 1rem;">Key Features</h3>
                    <p class="museum-project-descr">Choose a tour based on where you’re at and what you are interested
                        in
                    </p>
                    <div class="museum-small-filler"></div>
                    <div class="museum-image-container">
                        <img src="/src/assets/tour-flow.png" style="width: 100%; height: auto;" alt="">
                    </div>
                    <p class="museum-project-descr">Scan, save and interact with artwork that catch your attention</p>
                    <div class="museum-small-filler"></div>
                    <div class="museum-image-container">
                        <img src="/src/assets/interact-flow.png" style="width: 100%; height: auto;" alt="">
                    </div>
                    <p class="museum-project-descr">Find your saved items quickly and easily</p>
                    <div class="museum-small-filler"></div>
                    <div class="museum-image-container">
                        <img src="/src/assets/save-flow.png" style="width: 100%; height: auto;" alt="">
                    </div>
                    <div class="museum-filler"></div>
                    <h3>Accessibility</h3>
                    <div class="museum-small-filler"></div>
                    <div class="museum-image-container">
                        <img src="/src/assets/accessibility.png" style="width: 100%;" alt="">
                    </div>
                </div>
            </div>


        </div>
        <div @mousedown="down = true" class="museum-slider-button">
            <img class="museum-slider-icon" src="/src/assets/slider-icon.svg" alt="">
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
.museum-main {
    display: flex;
    position: absolute;
    top: 0;
    left: 0;
    width: 100vw;
    user-select: none;
    -webkit-user-select: none;
    z-index: 3;
}

.museum-back-wrapper:hover .back-button:after {
    content: 'Back';
    font-family: 'Helvetica Neue';
    font-size: 0.9rem;
    font-weight: 400;
    cursor: pointer;
}

.museum-left {
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

.museum-left::-webkit-scrollbar {
    display: none;
}

.museum-left {
    -ms-overflow-style: none;
    /* IE and Edge */
    scrollbar-width: none;
    /* Firefox */
}

.museum-right {
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

.museum-right::-webkit-scrollbar {
    display: none;
}

.museum-right {
    -ms-overflow-style: none;
    /* IE and Edge */
    scrollbar-width: none;
    /* Firefox */
}

.museum-categories {
    display: flex;
    column-gap: 1rem;
    align-items: center;
    justify-content: center;
    padding: 13rem 0 3rem 0;
    margin: 0 3rem 0 3rem;
    border-right: 1px dashed black;
}

.museum-table-container {
    margin: 0 3rem 0 3rem;
    display: grid;
    grid-template-columns: auto auto auto auto;
    gap: 0px;
    border: solid 0.5px;
}

.museum-filler {
    height: 4rem;
    width: 100%;
    border-left: 1px dashed black;
}

.museum-small-filler {
    height: 1rem;
    width: 100%;
    border-left: 1px dashed black;
}

.museum-project-descr {
    font-size: 1.1rem;
    line-height: inherit;
    margin-top: 1rem;
    margin-right: 1rem;
    padding-bottom: 1rem;
}

.museum-content {
    text-align: left;
    padding: 3rem;
    padding-top: 0;
}

.museum-image-container {
    width: calc(100% - 2rem);
    padding: 1rem;
    border: dashed 1px black;
}

.museum-grid-item {
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

.museum-slider-button {
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

.museum-slider-button:hover {
    cursor: grab;
}

.museum-slider-icon {
    width: 1.3rem;
    height: 1.3rem;
    pointer-events: none;
}
</style>