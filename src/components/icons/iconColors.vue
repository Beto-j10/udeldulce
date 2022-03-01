<script setup>
import { transform } from '@vue/compiler-core';
import { ref } from 'vue';

const props = defineProps({
    width: {
        type: Number,
        required: true,
    },
    position: {
        type: String,
        required: true,
    }
})

const width = ref(props.width);
const height = ref(0)
const top = ref('initial')
const left = ref('initial')
const bottom = ref('initial')
const right = ref('initial')
const transformOrigin = ref('initial')

function mediaQueryCheck(e) {
    if (e.matches) { // If media query matches
       resize(320)
    } else {
        resize(props.width)
    }
}
const mediaQuery = window.matchMedia("(min-width: 1024px)");
mediaQueryCheck(mediaQuery) // Call listener function at run time
mediaQuery.onchange = mediaQueryCheck; // Attach listener function on state changes





function resize(widthVal) {
    width.value = widthVal

    const legTriangle = width.value / Math.sqrt(2)
    height.value = width.value * 0.3

    if (props.position === 'top') {
        transformOrigin.value = "top left"
        top.value = (legTriangle - legTriangle / 3) + 'px'
        left.value = (-legTriangle / 3) + 'px'
    } else if (props.position === 'bottom') {
        transformOrigin.value = "bottom right"
        bottom.value = (legTriangle - legTriangle / 1.8) + 'px'
        right.value = (-legTriangle / 1.8) + 'px'
        // bottom = 0
        // right = 0
    }
}

</script>

<template>
    <svg
        :style="{ width: width + 'px', height: height + 'px', top: top, left: left, bottom: bottom, right: right, transformOrigin: transformOrigin }"
        viewBox="0 0 320 96"
        fill="none"
        xmlns="http://www.w3.org/2000/svg"
    >
        <rect width="320" height="96" fill="white" />
        <rect width="320" height="12" fill="#0181AF" />
        <rect y="14" width="320" height="12" fill="#D9CC39" />
        <rect y="28" width="320" height="12" fill="#6D639E" />
        <rect y="42" width="320" height="12" fill="#C88D49" />
        <rect y="56" width="320" height="12" fill="#A03E52" />
        <rect y="70" width="320" height="12" fill="#D9CC39" />
        <rect y="84" width="320" height="12" fill="#78AF4E" />
    </svg>
</template>

<style scoped>
svg {
    transform: rotate(-45deg);
    position: fixed;
    z-index: 2;
}
</style>
