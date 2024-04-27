<template>
    <div class="border-div">
        <div class="button-container">
            <div class="button-index">
                <img src="/src/assets/index-icon.svg" class="icon-design" alt="">
                <p class="button-label">Index</p>
            </div>
            <!-- <div class="button-graph">
                <img src="/src/assets/graph-icon.svg" class="icon-design" alt="">
            </div> -->
        </div>
    </div>
</template>

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
    display: flex;
    flex-direction: row;
    align-items: center;
    -webkit-backdrop-filter: blur(5px);
    backdrop-filter: blur(5px);
    width: max-content;
    column-gap: 0.3rem;
}

.button-index {
    background-color: #EDEBEE;
    width: fit-content;
    height: 3rem;
    column-gap: 0.7rem;
    border-radius: 1.5rem;
    text-align: center;
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: center;
    padding-right: 1.2rem;
    padding-left: 0.85rem;
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