<template>
  <section class="purchase">
    <div class="purchase__container">
      <div class="purchase__discount">
        Save 20%
      </div>
      <div class="product">
        <div class="product__description">
          <div class="product__icon">
            <element-svg
              file-name="product"
              width="72"
              height="81"
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
            <span class="price__currency">£</span>
            <span>34.</span>
            <span class="price__cents">99</span>
          </span>
          <span class="price__new">
            <span class="price__currency">£</span>
            <span>35.</span>
            <span class="price__cents">99</span>
          </span>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import ElementSvg from '@/components/UI/ElementSvg/ElementSvg.vue'
</script>

<style lang="scss" scoped>
.purchase {

  .purchase__discount {
    display: flex;
    justify-content: center;
    align-items: center;
    width: 285px;
    height: 40px;
    font-weight: 700;
    font-size: 21px;
    line-height: 24px;
    background-color: #8233FF;
    position: absolute;
    top: 0;
    transform: translate(0, -100%);
    left: 490px;
  }

  .purchase__container {
    position: relative;
    max-width: 1172px;
    height: 112px;
    padding: 16px 32px;
    display: flex;
    flex-flow: column nowrap;
    margin: 0 auto;
    background: linear-gradient(271.57deg, rgba(0, 168, 142, 0.4) 77.05%, rgba(126, 255, 51, 0.4) 100%), #23D1AE;

    .product {
      display: grid;
      grid-template-columns: [product-description] minmax(458px, 40%) [product-price] 285px [product-buy] 100%;
      justify-content: space-between;

      .product__description, .product__price {
        height: 100%;
        border-right: 1px solid rgba(255, 255, 255, .2);
      }

      .product__description {
        display: flex;
        align-items: center;
        flex-wrap: nowrap;
        gap: 32px;

        .product__heading {
          display: flex;
          flex-flow: column nowrap;
          gap: 7px;
          color: var(--c-black);
          font-style: normal;


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

            .rating {
              display: flex;
              justify-content: center;
              align-items: center;
              gap: 5px;

              .rating__icon {
                width: 16px;
                fill: var(--c-yellow);

                &:last-child {
                  svg {
                    fill: url("#half");
                  }
                }
              }
            }

            .reviews {
              font-weight: 300;
              font-size: 14px;
              line-height: 18px;

              .reviews__amount {

                &:hover {
                  color: var(--c-white);
                }
              }
            }
          }
        }
      }

      .product__price {
        //padding: 0 20px;
        display: flex;
        justify-content: center;
        align-items: center;
        flex-wrap: nowrap;
        gap: 12px;

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
      }
    }
  }
}
</style>
