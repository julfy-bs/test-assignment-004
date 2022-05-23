<template>
  <header class="header">
    <div class="header__container">
      <a
        class="logo"
        href="/"
      >
        <element-svg
          file-name="logo"
        />
      </a>
      <div class="header__content">
        <div class="header__currency">
          <select
            id="currencyPick"
            name="currency"
          >
            <option value="gbp">
              GBP
            </option>
          </select>
        </div>
      </div>
    </div>
  </header>
</template>

<script setup>
import ElementSvg from '@/components/UI/ElementSvg/ElementSvg.vue'

</script>

<style lang="scss" scoped>
.header {
  width: 100%;
  background-color: rgba(#1D1D1B, .4);
  padding: 0 1rem;

  .header__container {
    display: flex;
    justify-content: space-between;
    margin: 0 auto;
    max-width: var(--max-width);

    .logo {
      display: flex;
      align-items: center;
      height: 64px;
    }

    .header__content {
      display: flex;
      justify-content: flex-end;
      align-items: center;
      flex-grow: 1;

      .header__currency {
        select {
          min-width: 70px;
          min-height: 38px;
        }
      }
    }
  }
}
</style>
