<script setup>
import { ref,computed } from 'vue';
import { RouterLink } from 'vue-router';
const absOffset = ref(0);
const isInHome = ref(true);
const pageHeight = document.body.clientHeight;
window.addEventListener('scroll', () => {
  const scroll = window.pageYOffset || document.body.scrollTop;
  if (scroll < pageHeight) absOffset.value = (1 - (pageHeight - scroll) / pageHeight) * 2;
});
function setAbsOffsetAndIsHome(value) {
  absOffset.value = value;
  isInHome.value = !isInHome.value;
}
</script>

<template>
  <header id="nav" :style="{ backgroundColor: `rgba(255, 255, 255, ${absOffset})`}">
    <span id="title" class="scroll-change" :style="{
      opacity: absOffset
    }">fly tool</span>
    <div :style="{
          color: `rgba(${Math.floor(255 - absOffset * 255)}, ${Math.floor(255 - absOffset * 255)}, ${Math.floor(255 - absOffset * 255)}, 1)`
    }">
        <RouterLink to="/" :style="'margin-right: 5vw;' + (isInHome ? '' : 'opacity: 0.5;')"><span @click="setAbsOffsetAndIsHome(0)">Home</span></RouterLink>
        <RouterLink to="/about"  :style="isInHome ? 'opacity: 0.5;' : ''"><span @click="setAbsOffsetAndIsHome(1)">About</span></RouterLink>
    </div>
  </header>
</template>

<style scoped>
#nav {
    margin:0;
    display: flex;
    align-items: center;
    padding: 1em 3em;
    width: 100%;
    position: fixed;
    z-index: 100;
    color: rgba(0, 0, 0, .7);
}

#title {
    font-size: 2.5rem;
    font-weight: 500;
    margin-right: auto;
    color: black;
    font-family: 'Pacifico', cursive;
}

span + div > *{
    font-size: 1.3rem;
    font-weight: 500;
    color: inherit;
}

</style>