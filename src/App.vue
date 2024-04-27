<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router';
import { onBeforeMount, onMounted, ref, watch, type Ref } from 'vue'
import HelloWorld from './components/HelloWorld.vue';
import ViewButton from './components/ViewButton.vue';
import PrimaryButton from './components/PrimaryButton.vue';
import HeatmapButton from './components/HeatmapButton.vue'
import heatmapFactory from "heatmap.js"
import Home from './views/HomeView.vue';

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
</script>

<template>
  <div class="heatmapContainer" ref="heatmapContainer" style="width: 100%; height: 1000px; ">
    <nav>
      <p>Helen Hausdorf</p>
      <RouterLink class="view-button" to="/">
        <ViewButton></ViewButton>
      </RouterLink>
      <RouterLink class="about-button" to="/about">
        <PrimaryButton></PrimaryButton>
      </RouterLink>
      <HeatmapButton @click="toggleHeatmap" class="heatmap-button"></HeatmapButton>
    </nav>
    <main>
      <RouterView />
    </main>
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
</style>
