<template>
  <button class="button">
    <slot></slot>
  </button>
</template>

<style lang="scss">
.button {
  border: 1px solid $color-brand;
  border-radius: 4px;
  padding: 11px 15px;
  font-family: $font-family;
  font-weight: 700;
  font-size: 14px;
  line-height: 100%;
  color: $color-brand;
  background-color: $color-white;

  &--fill {
    color: $color-white;
    background-color: $color-brand;
  }

  &:hover {
    background-color: $color-brand;
    color: $color-white;
  }

  &--fill:hover {
    color: $color-white;
    background-color: $color-brand-two;
  }

  &--grey {
    border: 1px solid $color-font-second;
    color: $color-font-second;

    &:hover {
      background-color: $color-font-second;
      color: $color-white;
    }
  }
}
</style>
