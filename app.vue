<script setup>
import gsap from "gsap";
import { MorphSVGPlugin } from "gsap/MorphSVGPlugin";

gsap.registerPlugin(MorphSVGPlugin);

onMounted(() => {
  console.log(gsap.version);
  console.log(MorphSVGPlugin);

  gsap.to("#tag", {
    duration: 1,
    ease: "power1.inOut",
    repeat: -1,
    yoyo: true,
    repeatDelay: 1,
    morphSVG: "#moon",
  });
});
</script>

<template>
  <main class="wrapper">
    <svg xmlns="http://www.w3.org/2000/svg" width="300" height="300" viewBox="0 0 24 24">
      <path d="M19 21l-7-5-7 5V5a2 2 0 0 1 2-2h10a2 2 0 0 1 2 2z" id="tag" />
      <path d="M21 12.79A9 9 0 1 1 11.21 3 7 7 0 0 0 21 12.79z" id="moon" style="display: none;" />
    </svg>
  </main>
</template>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

.wrapper {
  width: 100%;
  height: 100vh;
  background-color: #d6fff0;
  display: flex;
  justify-content: center;
  align-items: center;
}

svg {
  border: 1px solid coral;
}

svg path {
  stroke: none;
  fill: teal;
}
</style>
