<template>
  <section class="hero">
    <div class="hero__container">
      <h1 class="hero__title">
        Don’t let malware defeat you
      </h1>
      <h2 class="hero__subtitle">
        Protect your devices with <br> a security suite made for gamers
      </h2>
      <ul class="strengths">
        <li
          v-for="strength in strengths"
          :key="strength.id"
          class="strengths__item"
        >
          <element-svg
            file-name="tick"
            class="strengths__list-style"
          />
          <span class="strengths__intro">
            {{ strength.intro }}:
          </span>
          <span class="strengths__description">
            {{ strength.description }}
          </span>
        </li>
      </ul>
      <div class="compatibility">
        Compatible with:
        <ul class="compatibility__list">
          <li class="compatibility__item">
            <a href="#">
              <element-svg
                file-name="windows"
                width="16"
              />
            </a>
          </li>
          <li class="compatibility__item">
            <a href="#">macOS</a>
          </li>
          <li class="compatibility__item">
            <a href="#">
              <element-svg
                file-name="android"
                width="20"
              />
            </a>
          </li>
          <li class="compatibility__item">
            <a href="#">
              iOS
            </a>
          </li>
        </ul>
      </div>
    </div>
    <home-purchase />
  </section>
</template>

<script setup>
import ElementSvg from '@/components/UI/ElementSvg/ElementSvg'
import HomePurchase from '@/components/HomePurchase/HomePurchase.vue'

const strengths = [
  {
    id: 0,
    intro: 'Gaming mode',
    description: 'Ensures optimal PC performance while you play'
  },
  {
    id: 1,
    intro: '100% detection rate',
    description: 'Never misses a threat'
  },
  {
    id: 2,
    intro: 'Cutting-edge cybersecurity',
    description: 'Runs on AI overseen by world-leading threat analysts'
  }
]
</script>

<style lang="scss" scoped>
.hero {
  padding: 50px 0;

  .hero__container {
    display: flex;
    flex-flow: column nowrap;
    margin: 0 auto;
    max-width: var(--max-width);
    padding-right: 35%;

    .hero__title {
      font-weight: 700;
      font-size: 64px;
      line-height: 68px;
      letter-spacing: -0.01em;
      margin: 0 0 35px;
    }

    .hero__subtitle {
      position: relative;
      font-weight: 300;
      font-size: 32px;
      line-height: 36px;
      margin: 0 0 50px;
      opacity: 0.8;

      &:before {
        content: '_______';
        position: absolute;
        top: -1.2em;
      }
    }

    .strengths {
      display: flex;
      flex-flow: column nowrap;
      gap: 20px;
      list-style: none;
      margin: 0 0 60px 30px;
      max-width: 500px;

      .strengths__item {
        position: relative;

        .strengths__intro, .strengths__description {
          font-size: 24px;
          line-height: 32px;
        }

        .strengths__intro {
          font-weight: 400;
          opacity: 1;
        }

        .strengths__description {
          opacity: .8;
          font-weight: 300;
        }

        .strengths__list-style {
          color: var(--c-green);
          position: absolute;
          top: 10px;
          left: -30px;
        }
      }
    }

    .compatibility {
      font-weight: 300;
      font-size: 16px;
      line-height: 20px;

      display: flex;
      flex-flow: row nowrap;
      gap: 24px;

      margin-bottom: 12px;

      .compatibility__list {
        display: flex;
        align-items: center;
        gap: 16px;
        list-style: none;
      }

      .compatibility__item, a {
        display: flex;
        align-items: center;
        justify-content: center;
      }

      .compatibility__item {
        font-size: 12px;

        &:not(&:last-child) {
          &::after {
            content: '';
            height: 24px;
            width: 1px;
            margin-left: 16px;
            background-color: var(--c-grey);
            opacity: 0.4;
          }
        }
      }
    }
  }
}
</style>
