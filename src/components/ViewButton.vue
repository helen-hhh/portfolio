<template>
    <div class="border-div">
        <div class="button-container">
            <div class="view-button-content">
                <div class="view-button-icon">
                    <img src="/src/assets/index-icon.svg" class="icon-design" alt="">
                </div>
                <p class="button-label">Index</p>
            </div>
            <!-- <div class="button-graph">
                <img src="/src/assets/graph-icon.svg" class="icon-design" alt="">
            </div> -->
        </div>
    </div>
</template>

<script setup>
const props = defineProps({
    highlight: String
})
</script>

<style scoped>
.border-div {
    color: #313149;
    padding: 1px;
    display: inline-block;
    position: relative;
    z-index: 0;
}

.border-div:before {
    content: "";
    position: absolute;
    z-index: -1;
    inset: 0;
    padding: 1px;
    border-radius: 33px;
    background: linear-gradient(140deg, #F7F5F0, #91908D);
    -webkit-mask:
        linear-gradient(#fff 0 0) content-box,
        linear-gradient(#fff 0 0);
    mask:
        linear-gradient(#fff 0 0) content-box,
        linear-gradient(#fff 0 0);
    -webkit-mask-composite: xor;
    mask-composite: exclude;
}

.button-container {
    background-color: rgba(255, 255, 255, 0.2);
    padding: 0.3rem;
    border-radius: 1.8rem;
    -webkit-backdrop-filter: blur(5px);
    backdrop-filter: blur(5px);
}

.view-button-content {
    border-radius: 1.8rem;
    display: flex;
    align-items: center;
    column-gap: 0.5rem;
    width: max-content;
    padding-right: 1rem;
    background-color: v-bind(highlight);
}

.view-button-content:hover {
    background-color: #EDEBEE;
}

.view-button-icon {
    background-color: #EDEBEE;
    width: 3rem;
    height: 3rem;
    border-radius: 1.5rem;
    text-align: center;
    display: flex;
    align-items: center;
    justify-content: center;
}

.button-graph {
    height: 3rem;
    width: 3rem;
    border-radius: 1.5rem;
    text-align: center;
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: center;
}

.button-graph:hover {
    background-color: #EDEBEE;
}

.icon-design {
    width: 1.3rem;
    height: 1.3rem;
}
</style>