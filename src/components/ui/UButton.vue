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

  &:hover {
    background-color: $color-brand;
    color: $color-white;
  }
}
</style>
