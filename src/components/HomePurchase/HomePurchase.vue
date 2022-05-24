<template>
  <section
    id="purchase"
    class="purchase"
  >
    <div class="purchase__container">
      <div
        ref="discount"
        class="purchase__discount"
      >
        Save 20%
      </div>
      <div class="product">
        <div class="product__description">
          <div class="product__icon">
            <element-svg
              file-name="product"
            />
          </div>
          <div class="product__heading">
            <div class="product__name">
              Kaspersky Internet Security
            </div>
            <div class="product__wrapper">
              <div class="rating">
                <div
                  v-for="star in 5"
                  :key="star"
                  class="rating__icon"
                >
                  <element-svg
                    file-name="star"
                  />
                </div>
              </div>
              <div class="reviews">
                <a
                  href="#"
                  class="reviews__amount"
                >
                  (1503 reviews)
                </a>
              </div>
            </div>
          </div>
        </div>
        <div class="product__price">
          <span class="price__old">
            <span>£</span>
            <span>34.</span>
            <span class="price__cents">99</span>
          </span>
          <span class="price__new">
            <span>£</span>
            <span>35.</span>
            <span class="price__cents">99</span>
          </span>
        </div>
        <div class="product__action">
          <div
            ref="select"
            class="action__select"
            aria-haspopup="true"
            aria-expanded="false"
          >
            <button
              class="select__button"
              role="button"
              @click="toggleSelect"
            >
              <span class="select__placeholder">
                <span>3 Devices, 1 year</span>
                <span class="select__arrow" />
              </span>
            </button>
            <div class="select__dropdown">
              <ul class="dropdown__list">
                <li class="dropdown__item">
                  1 Device, 1 Year £27.99
                </li>
                <li class="dropdown__item">
                  1 Device, 2 Years £43.99
                </li>
                <li class="dropdown__item active">
                  3 Devices, 1 Year £35.99
                </li>
                <li class="dropdown__item">
                  3 Devices, 2 Years £63.99
                </li>
                <li class="dropdown__item">
                  5 Devices, 1 Year £43.99
                </li>
                <li class="dropdown__item">
                  5 Devices, 2 Years £71.99
                </li>
              </ul>
            </div>
          </div>
          <button
            class="action__button"
            role="button"
          >
            Buy Now
          </button>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import ElementSvg from '@/components/UI/ElementSvg/ElementSvg.vue'
import { onBeforeUnmount, onMounted, ref } from 'vue'

const select = ref(null)
const discount = ref(null)


const openSelect = () => {
  select.value.classList.add('action__select--expanded')
  select.value.setAttribute('aria-expanded', true)
}

const closeSelect = () => {
  select.value.classList.remove('action__select--expanded')
  select.value.setAttribute('aria-expanded', false)
}
const toggleSelect = () => {
  const hasClass = select.value.classList.value.includes('action__select--expanded')
  const hasAttribute = select.value.getAttribute('aria-expanded')
  const isOpened = hasAttribute && hasClass
  if (isOpened) {
    closeSelect()
  } else {
    openSelect()
  }
}
</script>

<style lang="scss" scoped>
.purchase {
  padding-top: 83px;
  position: sticky;
  z-index: 2;
  top: 0;
  transform: translate(0, 80vh);

  @media (min-width: 1024px) {
    padding: 0;
    top: 40px;
    bottom: auto;
    display: block;
  }
}

.purchase__discount {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 50%;
  height: 40px;
  font-weight: 700;
  font-size: 21px;
  line-height: 24px;
  background-color: #8233FF;
  position: absolute;
  top: 0;
  transform: translate(0, -100%);
  left: 0;

  @media (min-width: 1024px) {
    width: 285px;
    left: 490px;
  }
}

.purchase__container {
  position: relative;
  max-width: minmax(var(--max-width), 100%);
  padding: 20px 16px;
  display: flex;
  flex-flow: column nowrap;
  margin: 0 auto;
  background: linear-gradient(271.57deg, rgba(0, 168, 142, 0.4) 77.05%, rgba(126, 255, 51, 0.4) 100%), #23D1AE;

  @media (min-width: 1024px) {
    padding: 16px 32px;
    max-width: 1172px;
  }
}

.product {
  display: flex;
  flex-flow: column nowrap;
  justify-content: space-between;

  @media (min-width: 1024px) {
    flex-direction: row;
    max-height: 112px;
  }
}

.product__description, .product__price {
  border: {
    right: none;
    bottom: 1px solid rgba(255, 255, 255, .2);
  }

  @media (min-width: 1024px) {
    border: {
      right: 1px solid rgba(255, 255, 255, .2);
      bottom: none;
    };
  }
}

.product__description {
  flex: 1 1 100%;
  display: flex;
  align-items: center;
  flex-wrap: nowrap;
  gap: 22px;
  padding-bottom: 20px;

  @media (min-width: 1024px) {
    flex: 1 1 40%;
    padding: 0;
    gap: 32px;
    min-width: 350px;
    max-width: 458px;
  }
}

.product__icon {
  width: 50px;
  height: 56px;

  @media (min-width: 1024px) {
    width: 72px;
    height: 81px;
  }
}

.product__heading {
  display: flex;
  flex-flow: column nowrap;
  gap: 7px;
  color: var(--c-black);
  font-style: normal;
}

.product__name {
  font-weight: 700;
  font-size: 21px;
  line-height: 24px;
}

.product__wrapper {
  display: flex;
  align-items: center;
  flex-wrap: nowrap;
  gap: 10px;
  font-weight: 300;
  font-size: 14px;
  line-height: 18px;
}

.rating {
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 5px;
}

.rating__icon {
  width: 16px;
  fill: var(--c-yellow);

  &:last-child {
    svg {
      fill: url(#half);
    }
  }
}

.reviews {
  font-weight: 300;
  font-size: 14px;
  line-height: 18px;
}

.reviews__amount {
  &:hover {
    color: var(--c-white);
  }
}

.product__price {
  flex: 1 1 100%;
  width: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-wrap: nowrap;
  gap: 12px;
  padding: 20px 0;

  @media (min-width: 1024px) {
    flex: 1 1 30%;
    max-width: 285px;
    padding: 1rem;
  }
}

.price__old {
  --fs-cents: 14px;
  font-weight: 300;
  font-size: 24px;
  line-height: 32px;
  color: var(--c-green-2);
  position: relative;

  &::after {
    content: '';
    display: block;
    width: 100%;
    position: absolute;
    bottom: 47%;
    border-bottom: 2px solid var(--c-green-2);
  }

  .price__cents {
    font-size: var(--fs-cents);
  }
}

.price__new {
  --fs-cents: 36px;
  font-weight: 700;
  font-size: 64px;
  line-height: 52px;
  letter-spacing: -.005em;
  color: var(--c-black);

  .price__cents {
    font-size: var(--fs-cents);
  }
}

.product__action {
  padding: 20px 0 0;
  flex: 1 1 100%;
  display: flex;
  flex-flow: column nowrap;
  justify-content: center;
  align-items: center;
  gap: 20px;

  @media (min-width: 1024px) {
    flex: 1 1 30%;
    flex-flow: row nowrap;
    padding: 1rem;
    gap: 24px;
  }
}

.action__select {
  --button-height: 48px;
  position: relative;
  width: 100%;
  color: var(--c-black);
  border: 2px solid var(--c-black);
  font-weight: 400;
  font-size: 16px;
  line-height: 20px;
  min-height: var(--button-height);
  display: flex;
  flex-direction: column;
  justify-content: center;
  background-color: var(--c-green);
  margin: auto;

  @media (min-width: 1024px) {
    width: 196px;

  }

  .select__dropdown {
    height: 0;
    overflow: hidden;
  }

  .select__button {
    width: 100%;
    height: var(--button-height);

    .select__placeholder {
      display: flex;
      justify-content: space-between;
      align-items: center;
      padding: 8px 12px;
      height: 100%;

      .select__arrow {
        width: 10px;
        height: 10px;
        border-top: 2px solid var(--c-black);
        border-right: 2px solid var(--c-black);
        transform: rotate(135deg);
      }
    }

    &:hover {
      cursor: pointer;
    }
  }

  &--expanded, [aria-expanded="true"] {
    border: 2px solid var(--c-black);

    .select__dropdown {
      height: 100%;
      overflow: visible;

      .dropdown__list {
        display: flex;
        flex-flow: column nowrap;
        font-weight: 400;
        font-size: 14px;
        line-height: 18px;

        .dropdown__item {
          height: 48px;
          padding: 15px 14px;
          background-color: var(--c-green);
          display: flex;
          align-items: center;

          &:hover {
            cursor: pointer;
          }
        }

        .dropdown__item.active {
          background-color: var(--c-green-3);

          &:hover {
            cursor: default;
          }
        }
      }
    }
  }
}

.action__button {
  min-width: 120px;
  width: 100%;
  height: 48px;
  background: #FF3748;
  border-radius: 3px;
  color: var(--c-white);

  @media (min-width: 1024px) {
    width: auto;
  }

  &:hover {
    cursor: pointer;
  }
}
</style>
