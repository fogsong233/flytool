<script setup>
import { ref } from 'vue';

const isOver = ref(false);
function animeStart(event) {
    isOver.value = true;
}
function animeEnd(event) {
    isOver.value = false;
}
</script>

<template>
  <a @mouseenter="animeStart" @mouseleave="animeEnd"><span><slot></slot><span class="mark" :style="{
    transform: isOver ? 'translateY(60%)' : 'translateY(150%)'
  }"></span></span></a>
</template>

<style scoped>
.mark {
    position: absolute;
    z-index: -100;
    left: 0;
    background-color: rgb(172, 251, 103);
    height: 40%;
    width: 100%;
    transition: transform .3s cubic-bezier(1, 0.06, 0.28, 1.43) .05s;
}

a {
    color: black;
}
</style>
