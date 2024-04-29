<script setup lang="ts">
import { ref } from "vue";

const snowGIF = ref(false);

const showSnow = () => {
  snowGIF.value = true;
};

const hideSnow = () => {
  snowGIF.value = false;
};
</script>

<template>
  <div class="about">
    <img class="snow-gif" src="/src/assets/giphy-2.gif" v-show="snowGIF" alt="">
    <div class="about-filler">
      <div style="width: 50%; height: 100%; border-right: dashed 1px black; margin-left: 1.25rem"></div>
      <div style="width: 50%; height: 100%; border-bottom: dashed 1px black; margin-right: 1.25rem"></div>
    </div>
    <div class="about-content">
      <div class="about-left">
        <h4 style="margin: 1.25rem;">My name is Helen Hausdorf. I’m a <em> communication design student</em> at <a
            href="https://www.burg-halle.de"> Burg
            Giebichenstein Halle</a> and UX/UI
          Designer at <a href="https://www.nadar.earth">nadar</a>.
          <br>
          I am interested in <em>user-centered design</em>; digital product design; coding; typography; research, data
          and
          numbers, but also the stories behind them. With my work I aim to create <em>friendly and accessible digital
            spaces</em>
          that have a positive impact on the user and their everyday life.
        </h4>
        <div class="contact">
          <div class="ready-button" @mouseover=showSnow @mouseleave=hideSnow>
            <section class="container">
              <div class="circle"></div>
            </section>
            <p>Ready to be snowed in</p>
          </div>
          <a href="https://www.instagram.com/helen.hhh/" target=”_blank”> <img class="about-icon"
              src="/src/assets/instagram.svg" alt=""></a>
          <a href="mailto:helen.hausdorf@gmail.com"> <img class="about-icon" src="/src/assets/mail-icon.png" alt=""></a>
          <a href="https://www.linkedin.com/in/helen-h-89876a272/" target=”_blank”> <img class="about-icon"
              src="/src/assets/linkedIn.svg" alt=""></a>
        </div>
        <div class="legal"
          style="display: flex; position: absolute; bottom: 0; margin-left: 1.25rem; column-gap: 1rem;">
          <RouterLink to="/imprint">
            <p>Imprint</p>
          </RouterLink>

          <RouterLink to="/privacy">
            <p>Data & Privacy Policy</p>
          </RouterLink>
        </div>
      </div>
      <div class="about-right">
        <div class="info-wrapper" style="border-top: 0;">
          <h4 style="margin-bottom: 1rem;">Education</h4>
          <p>October 2021 - Present
            <br>
            Pursuing a Bachelor of Arts degree in <span class="marked">Communication Design</span> at Burg
            Giebichenstein Halle
            <br>
            <br>
            August 2023 - Present
            <br>
            Further educating myself through online courses on the <span class="marked">Memorisely</span> platform in
            topics such as prototyping,
            UI
            design, Figma, and accessibility.
            <br>
            <br>
            2022 - 2023
            <br>
            Completed <span class="marked">Google UX Design Certificate</span> – These online courses offered by Google
            have equipped me with
            foundational knowledge in UX design, digital accessibility, design sprints, and associated
            research methodologies.
          </p>
        </div>
        <div class="info-wrapper">
          <h4 style="margin-bottom: 1rem;">Experience</h4>
          <p>
            June 2023 - Present
            <br>
            As a <span class="marked"> working student UX/UI designer at nadar</span>, a start-up focused on
            satellite-powered forest monitoring, I
            redesigned and implementing their website.
            Besides, my responsibilities include conceptualizing, structuring and designing the EUDR platform, alongside
            active involvement in front-end development. This
            role continually enhances my skills in design and development within the dynamic start-up environment.
            <br>
            <br>
            August - October 2022
            <br>
            During my <span class="marked">UX/UI Design internship at CLOTHESfriends</span>, a Swiss fashion-tech
            startup, I contributed to
            providing users with a contemporary and sustainable alternative to fast fashion through their app. Utilizing
            UX research
            methods, I identified pain points in the user flow and derived design proposals.
            <br>
            <br>
            October 2020 - March 2021
            <br>
            During my <span class="marked">internship at Studio Bosco</span>, I learned the basics of branding and
            workshop moderation. My work in
            web and app design projects on the subject of safe cycling and cargo bikes introduced me to the field of
            UX/UI design.
          </p>
        </div>
        <div class="info-wrapper">
          <h4 style="margin-bottom: 1rem;">Skills</h4>
          <p>
            UX/UI Design
            <br>
            Visual Design
            <br>
            Prototyping
          </p>
          <div style="display: flex; flex-direction: row; margin-top: 1rem;">
            <div style="width: 41.2%;">
              <p>
                Figma
                <br>
                HTML, CSS, JavaScript, Vue.js
                <br>
                Adobe Illustrator
                <br>
                Adobe Photoshop
                <br>
                Adobe InDesign
                <br>
                Webflow
              </p>
            </div>
            <div style="display: flex; flex-direction: column; row-gap: 0.38rem; margin-top: 0.2rem;">
              <img class="star-img" src="/src/assets/four-stars.png" alt="">
              <img class="star-img" src="/src/assets/three-stars.png" alt="">
              <img class="star-img" src="/src/assets/four-stars.png" alt="">
              <img class="star-img" src="/src/assets/two-stars.png" alt="">
              <img class="star-img" src="/src/assets/three-stars.png" alt="">
              <img class="star-img" src="/src/assets/four-stars.png" alt="">
            </div>
          </div>
        </div>
        <div class="info-wrapper">
          <h4>Books I recently read</h4>
          <div class="books">
            <div class="book-container">
              <img class="book-img" src="/src/assets/book01.jpg" alt="">
              <p class="book-title">On Earth We're Briefly Gorgeous</p>
            </div>
            <div class="book-container">
              <img class="book-img" src="/src/assets/book02.jpg" alt="">
              <p class="book-title">The Fraud</p>
            </div>
            <div class="book-container">
              <img class="book-img" src="/src/assets/book03.jpg" alt="">
              <p class="book-title">Crying in H Mart</p>
            </div>
            <div class="book-container">
              <img class="book-img" src="/src/assets/book04.jpg" alt="">
              <p class="book-title">Homegoing</p>
            </div>
            <div class="book-container">
              <img class="book-img" src="/src/assets/book05.jpg" alt="">
              <p class="book-title">Hässlichkeit</p>
            </div>
          </div>
          <div class="books">
            <div class="book-container">
              <img class="book-img" src="/src/assets/book06.jpg" alt="">
              <p class="book-title">Invisible Women</p>
            </div>
            <div class="book-container">
              <img class="book-img" src="/src/assets/book07.jpg" alt="">
              <p class="book-title">Die Dinge. Eine Geschichte der Frauen in 100 Objekten</p>
            </div>
            <div class="book-container">
              <img class="book-img" src="/src/assets/book08.jpg" alt="">
              <p class="book-title">The Design Of Everyday Things</p>
            </div>
            <div class="book-container">
              <img class="book-img" src="/src/assets/book09.jpg" alt="">
              <p class="book-title">Factfulness</p>
            </div>
            <div class="book-container">
              <img class="book-img" src="/src/assets/book10.jpg" alt="">
              <p class="book-title">Homo Deus</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style>
.star-img {
  height: 0.8rem;
}

.books {
  display: flex;
  flex-direction: row;
  column-gap: 1.25rem;
  margin-top: 1rem;
}

.book-container {
  display: flex;
  flex-direction: column;
  row-gap: 1rem;
  position: relative;
  width: 18%;
}

.book-img {
  height: auto;
  border-radius: 0.5rem;
  border: #EDEBEE solid 0.5px;
}

.book-title {
  position: absolute;
  align-self: center;
  padding: 1rem 1rem 0 1rem;
  bottom: 1rem;
  text-align: center;
  color: #90B7FF;
}

.book-container:hover .book-title {
  color: black;
}

.marked {
  background-color: #A3C3EB;
}

.snow-gif {
  position: absolute;
  width: 100%;
}

.ready-button:hover+.snow-gif {
  display: block;
}

.about-content {
  display: flex;
  margin: 0;
  padding: 0 1.25rem 1.25rem 1.25rem;
}

.about-filler {
  height: 10rem;
  width: 100%;
  display: flex;
  flex-direction: row;
}

.about-left {
  width: 50%;
  border: dashed 1px black;
  border-bottom: 0;
  border-right: 0;
  height: calc(100vh - 12rem);
  position: relative;
}

.contact {
  display: flex;
  flex-direction: row;
  margin: 1.25rem;
  column-gap: 2rem;
  align-items: center;
}

.about-icon {
  height: 2rem;
  width: auto;
}

.ready-button {
  height: 3rem;
  border-radius: 1.5rem;
  padding: 0 1.25rem 0 1.25rem;
  background-color: #EDEBEE;
  display: flex;
  flex-direction: row;
  column-gap: 1rem;
  justify-content: center;
  align-items: center;
}

.container {
  height: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
}

.circle,
.circle::before {
  content: " ";
  margin: 10px;
  width: 10px;
  height: 10px;
  border-radius: 50%;
  margin: 0 auto;
  transition: all 0.3s;
  background-color: #90B7FF;
}

.circle::before {
  animation: mymove 2s infinite;
  position: absolute;
  background-color: #D4E2FC
}

@keyframes mymove {
  50% {
    transform: scale(2);
    opacity: 0
  }

  100% {
    transform: scale(2);
    opacity: 0
  }
}

.about-right {
  width: 50%;
  height: calc(100vh - 10rem);
  overflow-y: scroll;
}

.about-right::-webkit-scrollbar {
  display: none;
}

.about-right {
  -ms-overflow-style: none;
  /* IE and Edge */
  scrollbar-width: none;
  /* Firefox */
}

.info-wrapper {
  border: dashed 1px black;
  border-bottom: 0;
  padding: 1.25rem;
}
</style>
