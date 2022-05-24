<template>
  <section class="cyber">
    <h2 class="cyber__title">
      Cybersecurity you can depend on
    </h2>
    <div class="cyber__wrapper">
      <div class="cyber__mode">
        <h3 class="mode__title">
          Gaming mode
        </h3>
        <div class="mode__description">
          We won’t disrupt you <br> while you are gaming.
        </div>
        <div class="mode__list">
          <element-list :list="preferences" />
        </div>
      </div>
      <div class="cyber__background-pc" />
      <div class="cyber__detection">
        <h3 class="detection__title">
          Malware detection <br> that can’t be beat
        </h3>
        <div class="detection__description">
          Powered by Artifical Intelligence <br>and over 1500 threat analysts.
        </div>
        <div class="detection__links" />
      </div>
    </div>
  </section>
</template>

<script setup>
import ElementList from '@/components/UI/ElementList/ElementList.vue'

const preferences = [
  'No virus scans', 'No software updates ', 'No notifications', 'Minimal CPU impact']
</script>

<style lang="scss" scoped>
.cyber {
  width: 100%;
  margin: 0 auto;
  display: flex;
  flex-flow: column nowrap;
  padding: 0;

  @media (min-width: 1024px) {
    padding: 90px 0 0;
  }
}

.cyber__title {
  text-align: center;
  font-weight: 700;
  font-size: 48px;
  line-height: 52px;
  letter-spacing: -0.03em;
  margin-bottom: 70px;
  display: none;

  @media (min-width: 1024px) {
    display: block;
  }
}

.cyber__wrapper {
  display: flex;
  flex-flow: column nowrap;
  position: relative;

  @media (min-width: 1024px) {
    flex-flow: row nowrap;
  }
}

.cyber__mode, .cyber__detection {
  padding: 35px calc(100% - var(--max-width));

  @media (min-width: 1024px) {
    padding: 50px 11vw;
  }
}

.mode__title, .detection__title {
  font-weight: 700;
  font-size: 36px;
  line-height: 40px;
  margin-bottom: 22px;

  @media (min-width: 1024px) {
    font-size: 40px;
    line-height: 44px;
  }
}

.mode__description, .detection__description {
  font-weight: 300;
  font-size: 24px;
  line-height: 27px;

  @media (min-width: 1024px) {
    font-size: 28px;
    line-height: 32px;
  }
}

.cyber__mode {
  background-color: var(--c-white);
  color: #444444;
  flex: 1 1 auto;
  margin: 34px 0 0;
  padding-bottom: 50px;
  position: relative;
  clip-path: polygon(0 0, 100% 0, 100% calc(100% - 13px), 0 100%);

  @media (min-width: 1024px) {
    flex: 1 1 50%;
    padding: 50px 11vw;
    clip-path: none;
    margin: 68px 0 0;
    z-index: 0;
  }

  .mode__list {
    font-weight: 300;
    font-size: 20px;

    @media (min-width: 1024px) {
      font-size: 24px;
    }
  }
}

.cyber__background-pc {
  background: linear-gradient(144.23deg, rgba(126, 255, 51, 0.4) 0%, rgba(35, 209, 174, 0.4) 79.06%), #23D1AE;
  width: 100%;
  height: 15px;
  transform: skew(-2deg) rotate(-2deg);
  transform-origin: top left;
  z-index: 1;

  @media (min-width: 1024px) {
    position: absolute;
    width: 150px;
    height: 100%;
    top: 0;
    left: 50%;
    transform: skew(-9deg);
    transform-origin: top left;
  }

  &:after {
    content: '';
    display: none;
    width: 318px;
    height: 504px;
    transform: translateX(-40%) skew(9deg);
    background: {
      image: url("../../static/images/pc.png");
      repeat: no-repeat;
      size: contain;
      position: left;
    };

    @media (min-width: 1024px) {
      display: block;
    }
  }
}

.cyber__detection {
  flex: 1 1 auto;
  background: linear-gradient(98.43deg, rgba(29, 29, 27, 0) -45.31%, #1D1D1B 57.89%), linear-gradient(180deg, rgba(29, 29, 27, 0) -3.51%, #1D1D1B 92.79%), linear-gradient(158.18deg, #00A88E 0%, rgba(1, 50, 35, 0) 100%);
  text-align: right;
  clip-path: polygon(0 21px, 100% 0, 100% 100%, 0 100%);
  transform: translateY(-3vh);

  @media (min-width: 1024px) {
    flex: 1 1 50%;
    height: 436px;
    margin: 0 0 68px;
    clip-path: none;
    transform: translateY(0);
  }
}
</style>
