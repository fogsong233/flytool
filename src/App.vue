<script setup>
import { RouterLink, RouterView } from 'vue-router'

import NavigatorBar from './components/NavigatorBar.vue';
</script>

<template>
  <NavigatorBar></NavigatorBar>
  <router-view v-slot="{ Component }">
    <transition name="fade">
      <component :is="Component" />
    </transition>
  </router-view>
</template>

<style scoped>
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.3s ease-in-out;
}

.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}
</style>
