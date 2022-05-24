<template>
  <div class="app__container">
    <home-header />
    <main>
      <home-hero />
      <home-purchase />
      <home-cybersecurity />
    </main>
  </div>
</template>
<script setup>
import HomeHeader from '@/components/HomeHeader/HomeHeader.vue'
import HomeHero from '@/components/HomeHero/HomeHero.vue'
import HomePurchase from '@/components/HomePurchase/HomePurchase.vue'
import HomeCybersecurity from '@/components/HomeCybersecurity/HomeCybersecurity.vue'

</script>

<style lang="scss">
:root {
  --font: 'Open Sans', sans;
  --max-width: 90%;
  --c-black: #1d1d1b;
  --c-white: #ffffff;
  --c-green: #23d1ae;
  --c-green-2: #006d5c;
  --c-green-3: #7fe3ce;
  --c-grey: #666666;
  --c-yellow: #ffe810;
  --bg: var(--c-black);

  @media (min-width: 1024px) {
    --max-width: 1110px;

  }
}

*, :before, :after {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

html {
  background-color: var(--bg);
}

body {
  width: 100%;
  min-width: 320px;
  min-height: 100vh;
  font-family: var(--font);
  line-height: 24px;
  font-size: 16px;
  font-weight: 400;
  opacity: 0.8;
  color: var(--c-white);

  @media (min-width: 768px) {
    background: linear-gradient(100deg, rgba(29, 29, 27, 0) 0%, #1D1D1B 55%), linear-gradient(180deg, rgba(29, 29, 27, 0) 0%, #1D1D1B 100%), linear-gradient(110deg, #23D1AE 0%, rgba(1, 50, 35, 0) 60%);
  }
}

a {
  text-decoration: none;
  color: inherit;
  transition: color .5s;

  &:hover {
    color: var(--c-green);
  }
}

ul, ol {
  list-style: none;
}

button {
  border: none;
  background-color: transparent;
}

.icon {
  transition: fill .5s, stroke .5s;
}

.app__container {
  display: flex;
  flex-direction: column;
  min-height: 100vh;
  transition: background-color .5s;
  padding: 0;
  margin: 0;
  background: {
    repeat: no-repeat;
    image: url("static/images/background.png");
    position: -30px 0;
    size: 110%;
  };

  @media (min-width: 768px) {
    background-position: 100% 0;
    background-size: auto;
  }
}
</style>
