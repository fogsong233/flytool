<template>
  <div class="about">
    <div>
      <div id="photo">
        <img :src="selfPhoto" />
      </div>
      <div id="desc">FogSong233<a href="github.com/fogsong233"><img :src="githubLogo" /></a></div>
    </div>
  </div>
</template>

<style>
@media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    display: flex;
    align-items: center;
    align-self: center;
  }
}

.about>div {
  display: flex;
  flex-direction: column;
  align-items: center;
  margin: -8em auto 0;
}

#photo {
  overflow: hidden;
  border-radius: 100%;
  height: 12vw;
  width: 12vw;
  box-shadow: #e7e7e7 9px 9px 20px, #e7e7e7 -3px -5px 20px;
}

#photo>img {
  height: 12vw;
  width: 12vw;
  object-fit: contain;
}

#desc {
  margin-top: .5em;
  font-weight: 300;
  font-size: 2rem;
}

#desc>a>img {
  height: 1.2em;
  padding-top: .4em;
}
</style>

<script setup>
import selfPhoto from "@/assets/photo.jpg";
import githubLogo from "@/assets/github.svg";

</script>