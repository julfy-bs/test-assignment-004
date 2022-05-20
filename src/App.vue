<template>
  <div class="app__container">
    <home-header />
    <home-hero />
  </div>
</template>
<script setup>
import HomeHeader from '@/components/HomeHeader/HomeHeader.vue'
import HomeHero from '@/components/HomeHero/HomeHero.vue'

</script>

<style lang="scss">
@import url('https://fonts.googleapis.com/css2?family=Open+Sans:wght@100;200;300;400;500;600;700;800;900');

:root {
  --font: 'Open Sans', sans;
  --max-width: 1110px;
  --c-bg: #1d1d1b;
  --c-white: #ffffff;
}
*, :before, :after {
  box-sizing: border-box;
}

body {
  width: 100%;
  min-width: 320px;
  min-height: 100vh;
  font-family: var(--font);
  line-height: 24px;
  font-size: 16px;
  font-weight: 400;
  margin: 0;
  padding: 0;
  background: linear-gradient(100deg, rgba(29, 29, 27, 0) 0%, #1D1D1B 55%), linear-gradient(180deg, rgba(29, 29, 27, 0) 0%, #1D1D1B 100%), linear-gradient(110deg, #23D1AE 0%, rgba(1, 50, 35, 0) 59.93%);
  opacity: 0.8;
  color: var(--c-white);
}

.app__container {
  display: flex;
  flex-direction: column;
  min-height: 100vh;
  transition: background-color .5s;
  padding: 0;
  margin: 0;
  height: calc(100vh - 64px);
  background: {
    repeat: no-repeat;
    image: url("static/images/background.png");
    position: 100% 0;
    size: auto;
  };
}
</style>
