<script setup></script>

<template>
  <ul class="tree">
    <li class="tree__parent tree__item">
      Название категории <span class="tree__item-quantity">3</span>
    </li>
    <ul class="tree__nested">
      <li class="tree__item">Название категории <span class="tree__item-quantity">3</span></li>
      <li class="tree__item">Название категории <span class="tree__item-quantity">3</span></li>
      <li class="tree__item tree__item--selected">
        Название категории <span class="tree__item-quantity">3</span>
      </li>
    </ul>
  </ul>
</template>

<style lang="scss">
ul {
  list-style-type: none;
  padding: 0;
}

.tree {
  font-family: $font-family;
  font-weight: 400;
  font-size: 14px;
  line-height: 114%;
  color: $color-font-main;

  &__item {
    padding: 7px 16px 7px 8px;
    display: flex;
    justify-content: space-between;

    &:hover {
      background-color: $color-icons;
      border-radius: 5px;
    }

    &--selected {
      background-color: $color-font-bg;
      border-radius: 5px;
      & .tree__item-quantity {
        color: $color-font-main;
      }
    }

    &-quantity {
      font-family: $font-family;
      font-weight: 400;
      font-size: 12px;
      line-height: 117%;
      text-align: right;
      color: $color-font-second;
    }
  }
}

.tree__nested {
  & .tree__item {
    padding-left: 40px;
  }
}
</style>
