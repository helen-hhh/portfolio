<template>
    <div class="border-div">
        <div class="button-container">
            <div class="button-content">
                <div class="button-icon">
                    <img src="/src/assets/sun-icon.svg" class="icon-design" alt="">
                </div>
                <p class="button-label">About me</p>
            </div>
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

.button-content {
    border-radius: 1.8rem;
    display: flex;
    align-items: center;
    column-gap: 0.5rem;
    width: max-content;
    padding-right: 1rem;
    background-color: v-bind(highlight);
}

.button-content:hover {
    background-color: #EDEBEE;
}

.button-icon {
    background-color: #EDEBEE;
    width: 3rem;
    height: 3rem;
    border-radius: 1.5rem;
    text-align: center;
    display: flex;
    align-items: center;
    justify-content: center;
}

.icon-design {
    width: 1.5rem;
    height: 1.5rem;
}
</style>