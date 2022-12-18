<script setup>
import LinkButton from './LinkButton.vue';

const props = defineProps(['name', 'content', 'links']);
</script>

<template>
    <div id="card-container">
        <div id="title">{{ props.name }}</div>
        <div id="link-list">
            <ul>
                <li class="info" v-for="info in props.content"><LinkButton :href="info[1]">{{ info[0] }}</LinkButton></li>

            </ul>
        </div>
    </div>
</template>

<style scoped>
#title {
    font-size: 2.5rem;
    font-weight: bold;
    margin-bottom: .5em;
}

#card-container {

    border: 5px solid;
    border-color: #eee;
    padding: 1em 1.5em;
    border-radius: 1em;
    transition: transform .25s cubic-bezier(1, 0.06, 0.28, 1.43) .05s;
}

ul {
    list-style: none;
    margin-block-start: 0em;
    padding-inline-start: .1em;
    font-size: 1.2rem;
}

ul>li {
    overflow: hidden;
    line-height: 1.1;
}



#card-container:hover {
    transform: scale(1.01) translateY(-10px) rotateX(-10deg);
}

ul {
    height: 50vh;
    overflow: auto;
}

ul > * + * {
    margin-top: .8em;
}
#extra {
    display: none;
    opacity: 0;
    transition: opacity .25s cubic-bezier(1, 0.06, 0.28, 1.43) .05s;
}

@media screen and (max-width: 800px) {
    #card-container {
        min-width: 60vw;
    }
}

@media screen and (min-width: 900px) {
    #card-container {
        min-width: 30%;
    }
}

@media screen and (min-width: 1648px) {
    #card-container {
        min-width: 25%;
    }
}
</style>
