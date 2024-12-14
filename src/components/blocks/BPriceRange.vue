<script setup>
import UInputPrice from '../ui/UInputPrice.vue'
</script>

<template>
  <fieldset class="price-range">
    <legend class="price-range__legend">Цена</legend>
    <div class="price-range__container">
      <UInputPrice type="number" min="0" max="100000" placeholder="Цена" range-name="от" />
      <span class="price-range__spliter" />
      <UInputPrice type="number" min="0" max="100000" placeholder="Цена" range-name="до" />
    </div>
  </fieldset>
</template>

<style lang="scss">
.price-range {
  border: none;
  display: flex;

  &__legend {
    font-family: $font-family;
    font-weight: 700;
    font-size: 16px;
    line-height: 125%;
    color: $color-font-main;
    align-self: center;
    margin: 0 auto;
    margin-bottom: 16px;
  }

  &__container {
    display: flex;
    align-items: center;
    gap: 16px;
  }

  &__spliter {
    width: 10px;
    height: 1px;
    border: 1px solid $color-border;
  }
}
</style>
