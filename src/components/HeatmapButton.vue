<template>
    <div class="border-div">
        <div class="button-container">
        </div>
    </div>
</template>
<style scoped>
.border-div {
    color: #313149;
    padding: 1px;
    display: inline-block;
    position: fixed;
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
    background: radial-gradient(83.14% 83.14% at 27.08% 25%, rgba(237, 137, 114, 0.90) 0%, rgba(237, 224, 115, 0.90) 22.5%, rgba(145, 237, 112, 0.90) 33.5%, rgba(113, 238, 232, 0.90) 53%, rgba(111, 128, 238, 0.90) 78.5%, rgba(156, 156, 228, 0.90) 100%);
    border-radius: 1.8rem;
    width: 3.6rem;
    height: 3.6rem;
    -webkit-backdrop-filter: blur(5px);
    backdrop-filter: blur(5px);
}
</style>