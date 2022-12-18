<script setup>
import cover from '@/assets/cover.jpg'
</script>

<template>
    <div :style="{
        height: '100vh',
        width: '100vw',
        background: `linear-gradient(rgba(0, 0, 0, 0.6), rgba(0, 0, 0, 0.7)), url(${cover}) `
    }" id="cover">
        <div>fly tool</div>
    </div>
</template>

<style scoped>
@keyframes flow {

    0% {
        transform: translateX(10px) rotateY(10deg) skew(5deg, -5deg);
    }

    50% {
        transform: translateX(-10px) rotateY(-10deg) skew(-5deg, 5deg);
    }

    100% {
        transform: translateX(10px) rotateY(10deg) skew(5deg, -5deg);
    }
}

#cover {
    display: flex;
    color: rgba(255, 255, 255, .9);
    align-items: center;
}

#cover>div {
    margin: -1.5em auto 0;
    font-size: 10vw;
    font-family: 'Pacifico', cursive;
    animation: flow 2s ease-in-out .1s infinite;
}
</style>
