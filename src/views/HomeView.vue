<script setup lang="ts">
//images for project overview index
import { ref } from "vue";
import ProjectView from '../components/ProjectView.vue'
import GenderGapView from './GenderGapView.vue';
import AdaLovelaceView from './AdaLovelaceView.vue'
import Print from './Print.vue'
import p11ImageSource from "../assets/gender-data-gap-01.png"

import p12ImageSource from '../assets/gender-data-gap-02.png';
import p21ImageSource from '../assets/ada-lovelace.png';
import p3bgImageSource from '../assets/nadar-bg.png'
import p31ImageSource from '../assets/nadar-01.png';
import p32ImageSource from '../assets/nadar-02.png';
import p41ImageSource from '../assets/hidden-stories-01.png';
import p42ImageSource from '../assets/hidden-stories-02.png';
import p51ImageSource from '../assets/reise-01.png';
import p61ImageSource from '../assets/print-01.png';
import p62ImageSource from '../assets/print-03.png';
import p63ImageSource from '../assets/print-04.png';
import p71ImageSource from '../assets/creative-coding-01.png';
import p72ImageSource from '../assets/creative-coding-02.png';

const viewBgImg = ref(false);
const viewBgImg2 = ref(false);
const viewBgImg3 = ref(false);
const viewBgImg4 = ref(false);
const viewBgImg5 = ref(false);
const viewBgImg6 = ref(false);
const viewBgImg7 = ref(false);
</script>

<template>
  <div>
    <img class="bgImg lightenMode" src="/src/assets/gender-data-gap-bg.svg" v-show="viewBgImg" alt="">
    <img class="bgImg screenMode" src="/src/assets/ada-lovelace-bg.png" v-show="viewBgImg2" alt="">
    <img class="bgImg lightenMode" src="/src/assets/nadar-bg.png" v-show="viewBgImg3" alt="">
    <img class="bgImg lightenMode" src="/src/assets/hidden-stories-bg.png" v-show="viewBgImg4" alt="">
    <img class="bgImg lightenMode" style="opacity: 50%;" src="/src/assets/reise-bg.png" v-show="viewBgImg5" alt="">
    <img class="bgImg screenMode" src="/src/assets/print-bg.png" v-show="viewBgImg6" alt="">
    <img class="bgImg" src="/src/assets/creative-coding-bg.png" v-show="viewBgImg7" alt="">
  </div>
  <div class="projects-div">
    <ProjectView v-slot="slotProps" @mouseenter="viewBgImg = true" @mouseleave="viewBgImg = false" class="project1"
      title="Gender Data Gap (in Design)" desc="A translation of a book into the digital" year="2023/24" team="Just me"
      tools="Figma, VSCode, Obsidian" :imageSource1="p11ImageSource" :imageSource2="p12ImageSource"
      category_title="Dev Web Typo" popOutPage="GenderGapView">
      <GenderGapView @close="slotProps.close()" />
    </ProjectView>

    <ProjectView v-slot="slotProps" @mouseenter="viewBgImg2 = true" @mouseleave="viewBgImg2 = false" class="project2"
      title="Untold Stories – 
Ada Lovelace" desc="An editorial design and font sketch about Ada Lovelace" year="2022" team="Just me"
      tools="InDesign, p5.js, Glyphs, Illustrator" :imageSource1="p21ImageSource" category_title="Typo Creative Edit">
      <AdaLovelaceView @close="slotProps.close()" />
    </ProjectView>

    <!-- <ProjectView @mouseenter="viewBgImg3 = true" @mouseleave="viewBgImg3 = false" class="project3" title="nadar"
      desc="UX/UI for a start-up building a platform for satellite-powered forest monitoring" year="2023/24"
      team="Caroline Busse, Marco Eberle" tools="Figma, VSCode, Webflow, Hotjar" category_title="Web UX Dev Research"
      :imageSource1="p31ImageSource" :imageSource2="p32ImageSource" :bgsrc="p3bgImageSource">
    </ProjectView> -->

    <ProjectView @mouseenter="viewBgImg4 = true" @mouseleave="viewBgImg4 = false" class="project4"
      title="Hidden Stories Museum" desc="An app for visitors to save and recall their favorite museum exhibits."
      year="2022" team="Just me" tools="Figma" :imageSource1="p41ImageSource" :imageSource2="p42ImageSource"
      category_title="UX Research Illu">
    </ProjectView>

    <ProjectView @mouseenter="viewBgImg7 = true" @mouseleave="viewBgImg7 = false" class="project7"
      title="Creative Coding Sketches" desc="Selection of creative coding projects made with p5.js" year="2021"
      team="Just me" tools="VSCode, p5.js" :imageSource1="p71ImageSource" :imageSource2="p72ImageSource"
      category_title="Dev Creative">
    </ProjectView>

    <ProjectView @mouseenter="viewBgImg5 = true" @mouseleave="viewBgImg5 = false" class="project5"
      title="Reise ans Ende des Bettes" desc="A translation of a text into a publication and a website" year="2023"
      team="Just me" tools="VSCode, InDesign" :imageSource1="p51ImageSource" category_title="Edit Typo Dev">
    </ProjectView>

    <ProjectView v-slot="slotProps" @mouseenter="viewBgImg6 = true" @mouseleave="viewBgImg6 = false" class="project6"
      title="Print Media - 
a selection" desc="Selection of posters, postcards and other print media" year="2023/24" team="various"
      tools="InDesign, Figma" :imageSource1="p61ImageSource" :imageSource2="p62ImageSource"
      category_title="Edit Typo Graphic" :imageSource3="p63ImageSource">
      <Print @close="slotProps.close()" />
    </ProjectView>
    <footer
      style="position:relative; display: flex; flex-direction: row; margin-top: 6rem; width: 100%;justify-content: center;">
      <p style="position: absolute; left: 0; bottom: 0.5rem;">© 2024 Helen Hausdorf. All rights reserved</p>
      <p style="position: absolute; bottom: 0.5rem;">Coded with 🩵 and 🌞 by me</p>
      <p style="position: absolute; right: 0; bottom: 0.5rem;">Erasmus Application EKA - Digital Product Design</p>
    </footer>
  </div>

</template>

<style>
.bgImg {
  position: fixed;
  z-index: -1;
  top: 0;
  left: 50%;
  transform: translate(-50%);
  width: 100vw;
  animation: background-animation 1s ease;
  -webkit-animation: background-animation 1s ease;
}

.projects-div {
  padding: 1.25rem;
  padding-top: 14rem;
  height: calc(100vh - 15.25rem);
  overflow-y: scroll;
}

.lightenMode {
  mix-blend-mode: lighten;
}

.colorMode {
  mix-blend-mode: color;
}

.screenMode {
  mix-blend-mode: screen;
}

.exclusionMode {
  mix-blend-mode: color-dodge;
  opacity: 60%;
}




@keyframes background-animation {


  0% {
    filter: blur(1em);
    opacity: 0;
  }

  100% {
    filter: blur(0px);
    opacity: 1;
  }
}
</style>
