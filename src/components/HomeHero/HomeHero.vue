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
        <h3 class="compatibility__title">
          Compatible with:
        </h3>
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
  </section>
</template>

<script setup>
import ElementSvg from '@/components/UI/ElementSvg/ElementSvg'

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
  @media (min-width: 768px) {
    padding: 50px 0 0;
  }
}

.hero__container {
  display: flex;
  flex-flow: column nowrap;
  margin: 0 auto;
  max-width: var(--max-width);
  padding: 356px 0 0 0;

  @media (min-width: 768px) {
    padding: 0 35% 0 0;
  }
}

.hero__title {
  letter-spacing: -0.01em;
  margin: 0 0 35px;
  font-weight: 700;
  font-size: 36px;
  line-height: 40px;

  @media (min-width: 768px) {
    font-size: 64px;
    line-height: 68px;
  }
}

.hero__subtitle {
  position: relative;
  font-weight: 300;
  margin: 0 0 25px;
  opacity: 0.8;
  font-size: 24px;
  line-height: 27px;

  @media (min-width: 768px) {
    font-size: 32px;
    line-height: 36px;
    margin: 0 0 50px;
  }

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
}

.strengths__item {
  position: relative;
}

.strengths__intro, .strengths__description {
  font-size: 20px;
  line-height: 32px;

  @media (min-width: 768px) {
    font-size: 24px;
    line-height: 32px;
  }
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

.compatibility {
  display: flex;
  flex-flow: column wrap;
  gap: 13px;
  margin-bottom: 12px;
  padding: 0 30px;

  @media (min-width: 768px) {
    flex-flow: row nowrap;
    padding: 0;
    gap: 24px;
  }
}

.compatibility__title {
  font-weight: 400;
  font-size: 12px;
  line-height: 16px;

  @media (min-width: 768px) {
    font-size: 16px;
    line-height: 20px;
  }
}

.compatibility__list {
  display: flex;
  justify-content: center;
  align-items: center;
  list-style: none;

  @media (min-width: 768px) {
    justify-content: flex-start;
    font-size: 16px;
    line-height: 20px;
    gap: 16px;
  }
}

.compatibility__item, a {
  display: flex;
  align-items: center;
  justify-content: center;
}

.compatibility__item {
  font-size: 12px;
  position: relative;

  &:not(&:last-child) {
    &::after {
      content: '';
      height: 24px;
      width: 1px;
      margin: 0 7vw;
      background-color: var(--c-grey);
      opacity: 0.4;

      @media (min-width: 768px) {
        justify-content: flex-start;
        margin: 0 0 0 16px;
      }
    }
  }
}
</style>
