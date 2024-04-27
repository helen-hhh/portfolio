<template>
    <div>
        <div class="project" @click="show = true">
            <div class="meta-information">
                <div class="title-div">
                    <h1 class="project-title">{{ title }}</h1>
                    <div class="filler"></div>
                    <LearnMoreButton @click="show = true" class="learn-more-button"></LearnMoreButton>
                </div>
                <div class="info-div">
                    <p>{{ desc }}</p>
                    <div
                        style="height: 1px; background-color: black; width: 3rem; margin-top: 0.5rem; margin-bottom: 0.5rem;">
                    </div>
                    <p style="margin-bottom: 1.25rem;">
                        Year: {{ year }} <br>
                        Team: {{ team }} <br>
                        Tools: {{ tools }}
                    </p>
                    <div class="category-div">
                        <Category v-for="title in category_title!.split(' ')" :title="title"></Category>
                    </div>
                </div>
            </div>
            <div class="project-images">
                <img class="project-img" :src="imageSource1" alt="">
                <img class="project-img" :src="imageSource2" alt="">
                <img class="project-img" :src="imageSource3" alt="">
            </div>
        </div>
        <slot v-if="show" :close="() => show = false"></slot>
    </div>
</template>
<script setup lang="ts">
import GenderGapView from '@/views/GenderGapView.vue';
import Category from './Category.vue'
import LearnMoreButton from './LearnMoreButton.vue';
import { ref } from 'vue';

const show = ref < boolean > (false);

function close() {
    show.value = false;
}

const props = defineProps({
    imageSource1: String,
    imageSource2: String,
    imageSource3: String,
    title: String,
    desc: String,
    year: String,
    team: String,
    tools: String,
    category_title: String,
});
</script>

<style scoped>
@font-face {
    font-family: 'PPMondwest';
    src: url('./src/assets/PPMondwest-Regular.otf');
}

.project-title {
    font-family: 'PPMondwest';
    font-size: 2rem;
    font-style: normal;
    font-weight: 400;
    line-height: normal;
    margin: 0%;
    padding: 0;
}

.project {
    border-top: 1px solid black;
    display: flex;
    /* Alle Flex-Elemente in der Hauptachse strecken */
    column-gap: 1.5rem;
    padding-top: 1.25rem;
    padding-bottom: 2rem;
}

.meta-information {
    width: 42%;
    display: flex;
    column-gap: 1rem;
}

.title-div {
    width: 100%;
    height: auto;
    padding-right: 2rem;
    display: flex;
    flex-direction: column;
    align-items: stretch;
    justify-content: space-between;
}

.filler {
    flex: 1 0 0;
    align-self: stretch;
    height: 100%;
}

.project:hover .learn-more-button:after {
    content: 'Learn more';
    font-family: 'Helvetica Neue';
    font-size: 1rem;
    font-weight: 400;
}

.info-div {
    width: 100%;
}

.category-div {
    display: flex;
    flex-wrap: wrap;
    column-gap: 0.6rem;
    row-gap: 0.6rem;
}

.project-images {
    width: 58%;
    display: flex;
    gap: 1rem;
}

.project-img {
    width: auto;
    height: 13.3rem;
}
</style>