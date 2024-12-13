<template>
  <label class="input">
    <!-- <span class="input__label"><slot name="inputLabel"></slot></span> -->
    <div class="input__body">
      <input :type="type" :placeholder="placeholder" :disabled="disabled" class="input__field" />
      <IconSearch class="input__icon-search" />
      <span class="input__righticon"><slot name="inputRightIcon"></slot></span>
    </div>
  </label>
</template>

<script setup>
import IconSearch from '../icons/IconSearch.vue'
const props = defineProps({
  disabled: {
    type: Boolean,
    required: false,
    default: false,
  },
  placeholder: {
    type: String,
    required: false,
    default: '',
  },
  type: {
    type: String,
    required: false,
    default: 'text',
  },
})
</script>

<style lang="scss">
.input {
  display: flex;
  flex-direction: column;
  width: 100%;
  justify-content: center;
  position: relative;

  &__icon-search {
    fill: #aaaaaa;
    width: 24px;
    height: 24px;
    position: absolute;
    left: 16px;
    transition: fill 1s;
  }
  &__icon {
    display: flex;
    align-self: flex-end;
  }

  &__body {
    display: flex;
    align-items: center;
  }
  &__field {
    font-family: var(--second-family);
    font-weight: 400;
    font-size: 16px;
    line-height: 150%;
    color: #5a5a5a;
    border: 1px solid $color-border;
    border-radius: 10px;
    padding: 11px 16px 11px 48px;
    width: 100%;

    &:focus {
      border: 1px solid $color-brand-two;
      transition: border 0.5s;

      & ~ .input__icon-search {
        fill: #5a5a5a;
      }
    }

    &::placeholder {
      color: #ababab;
    }
    &:focus {
      outline: none;
    }
  }
}
</style>
