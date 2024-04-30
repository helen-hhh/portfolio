<script setup lang="ts">
import { RouterLink, RouterView, onBeforeRouteLeave } from 'vue-router';
import { onBeforeMount, onMounted, ref, watch, type Ref } from 'vue'
import HelloWorld from './components/HelloWorld.vue';
import ViewButton from './components/ViewButton.vue';
import PrimaryButton from './components/PrimaryButton.vue';
import HeatmapButton from './components/HeatmapButton.vue'
import heatmapFactory from "heatmap.js"
import Home from './views/HomeView.vue';
import { useRoute } from 'vue-router';

const route = useRoute();

//heatmap
const heatmapContainer = ref<HTMLDivElement>();
let heatmapInterface: any = null;
let showHeatMap = false;
let points: Ref<Array<{ x: number, y: number, value: number }>> = ref([]);

onMounted(() => {
  if (heatmapContainer.value) {
    heatmapInterface = heatmapFactory.create({
      container: heatmapContainer.value,
      maxOpacity: .6,
      radius: 50,
      blur: .90,
    })
    heatmapContainer.value!.ontouchmove = (e: TouchEvent) => {
      e.preventDefault();

      let x, y;
      if (e.touches) {
        x = e.touches[0].pageX;
        y = e.touches[0].pageY;
        points.value.push({ x: x!, y: y!, value: 1 });
      }
      if (showHeatMap) {
        heatmapInterface.setData({ max: 10, data: points.value });
      }
    };

    heatmapContainer.value!.onmousemove = (e) => {
      let x = e.layerX;
      let y = e.layerY;
      points.value.push({ x: x, y: y, value: 1 });
      if (showHeatMap) {
        try {
          heatmapInterface.setData({ max: 10, data: points.value });
        } catch (error) {
          console.error(error);
          points.value = [];
        }
      }
    }
    const canvas = document.getElementsByClassName("heatmap-canvas")[0] as HTMLCanvasElement;
    canvas.style.pointerEvents = "none";
  }
})

function toggleHeatmap() {
  showHeatMap = !showHeatMap;
  heatmapInterface.setData({ data: [] })
}

onBeforeMount(() => {
  heatmapInterface = null;
})

let highlightHome = ref('#EDEBEE');
let highlightAbout = ref('none');

watch(() => route.name, () => {

  highlightHome.value = 'none';
  highlightAbout.value = 'none';
  if (route.name == "home")
    highlightHome.value = '#EDEBEE';

  if (route.name == "about")
    highlightAbout.value = '#EDEBEE';



});
</script>

<template>
  <div class="heatmapContainer" ref="heatmapContainer" style="width: 100%; height: 1000px; ">
    <nav>
      <p>Helen Hausdorf</p>
      <RouterLink class="view-button" to="/">
        <ViewButton :highlight="highlightHome"></ViewButton>
      </RouterLink>
      <RouterLink class="about-button" to="/about">
        <PrimaryButton :highlight="highlightAbout"></PrimaryButton>
      </RouterLink>
      <HeatmapButton @click="toggleHeatmap" class="heatmap-button"></HeatmapButton>
    </nav>
    <main>
      <RouterView />
    </main>
  </div>

  <!-- Mobiler Platzhalter, wird nur auf screens kleiner als 768px angezeigt -->
  <div class="mobile-placeholder">
    <p>Helen Hausdorf</p>
    <div class="mobile-filler">
      <div class="mobile-filler-div"></div>
    </div>
    <div class="mobile-text">
      <h1 class="mobile-h1">Please view this website
        on a larger device</h1>
      <p>Looks like you're browsing on a mobile device. My portfolio is not mobile-friendly (yet). Please try again on a
        bigger screen!
        <br>
        <br>
        If you have any questions or need assistance, feel free to reach out to me at <a
          href="mailto:helen.hausdorf@gmail.com">helen.hausdorf@gmail.com</a>
        <br>
        <br>
        Thank you for your understanding!
      </p>
    </div>
    <div class="mobile-filler-bottom"></div>
  </div>
</template>



<style scoped>
.heatmapContainer {
  height: 100%;
}

nav {
  display: flex;
  position: fixed;
  top: 2rem;
  align-items: center;
  justify-content: space-between;
  text-align: center;
  z-index: 4;
  margin-left: 1.25rem;
}

.about-button {
  position: fixed;
  right: 1.25rem;
}

.view-button {
  position: fixed;
  left: 50%;
  transform: translate(-50%);
}

.heatmap-button {
  position: fixed;
  bottom: 1.25rem;
  right: 1.25rem;
}

.mobile-placeholder {
  display: none;
}

@media only screen and (max-width: 768px) {

  /* For mobile phones: */
  .heatmapContainer {
    display: none;
  }

  .mobile-placeholder {
    display: block;
    text-align: center;
    height: 100vh;
    width: 100vw;
    overflow-y: scroll;
    padding-top: 1.25rem;
  }

  .mobile-text {
    margin: 0 1.25rem 0 1.25rem;
    padding: 1.25rem;
    border-left: dashed 1px black;
    border-bottom: dashed 1px black;
    padding-bottom: 10vh;
  }

  .mobile-h1 {
    font-size: 2.1rem;
    margin-bottom: 2rem;
  }

  .mobile-filler {
    width: 100%;
    margin-top: 1rem;
  }

  .mobile-filler-div {
    width: 50%;
    height: 10vh;
    border-right: dashed 1px black;
  }

  .mobile-filler-bottom {
    width: calc(100% - 1.25rem);
    height: 20vh;
    border-right: dashed 1px black;
    margin-right: 1.25rem;
  }
}
</style>
