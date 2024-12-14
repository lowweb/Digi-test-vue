<script setup>
import UInput from '../ui/UInput.vue'
import UCheckBox from '../ui/UCheckBox.vue'
const props = defineProps({
  withSearch: {
    type: Boolean,
    required: false,
    default: false,
  },
  legend: {
    type: String,
    required: true,
    default: '',
  },
})
</script>

<template>
  <fieldset class="checkbox-group">
    <legend
      class="checkbox-group__legend"
      :class="{ 'checkbox-group__legend--center': !withSearch }"
    >
      {{ legend }}
      <button class="checkbox-group__clean" v-if="withSearch">Очистить</button>
    </legend>
    <UInput type="text" :slim="true" placeholder="Поиск" v-if="withSearch" />
    <ul class="checkbox-group__container">
      <li class="checkbox-group__item">
        <UCheckBox label="Атрибут" />
        <span class="checkbox-group__item-quantity">3</span>
      </li>
      <li class="checkbox-group__item">
        <UCheckBox label="Атрибут" />
        <span class="checkbox-group__item-quantity">3</span>
      </li>
      <li class="checkbox-group__item">
        <UCheckBox label="Атрибут" />
        <span class="checkbox-group__item-quantity">3</span>
      </li>
      <li class="checkbox-group__item">
        <UCheckBox label="Атрибут" />
        <span class="checkbox-group__item-quantity">3</span>
      </li>
      <li class="checkbox-group__item">
        <UCheckBox label="Атрибут" />
        <span class="checkbox-group__item-quantity">3</span>
      </li>
      <li class="checkbox-group__item">
        <UCheckBox label="Атрибут" />
        <span class="checkbox-group__item-quantity">3</span>
      </li>
    </ul>
  </fieldset>
</template>

<style lang="scss">
.checkbox-group {
  border: none;
  display: flex;
  flex-direction: column;
  gap: 16px;

  &__legend {
    font-family: $font-family;
    font-weight: 700;
    font-size: 16px;
    line-height: 125%;
    color: $color-font-main;
    align-self: center;
    margin-bottom: 16px;
    display: flex;
    align-items: end;
    justify-content: space-between;
    width: 100%;

    &--center {
      justify-content: center;
    }
  }

  &__clean {
    font-family: $font-family;
    font-weight: 400;
    font-size: 12px;
    line-height: 100%;
    text-decoration: underline;
    text-decoration-skip-ink: none;
    text-align: right;
    color: $color-font-second;
    border: none;
    background-color: transparent;
    cursor: pointer;
  }

  &__container {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 12px;
  }

  &__item {
    display: flex;
    justify-content: space-between;
    align-items: center;
    width: 100%;
    padding-right: 16px;

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
</style>
