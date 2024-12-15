<script setup>
import { ref } from 'vue'
const value = ref('')
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
  rangeName: {
    type: String,
    required: false,
    default: 'text',
  },
})
</script>

<template>
  <label class="input">
    <div class="input__body">
      <input
        :type="type"
        :placeholder="placeholder"
        :disabled="disabled"
        v-model="value"
        class="input__field"
      />
      <span class="input__range-name">{{ rangeName }}</span>
    </div>
  </label>
</template>

<style lang="scss" scoped>
.input {
  display: flex;
  flex-direction: column;
  width: 100%;
  justify-content: center;
  position: relative;

  &__range-name {
    font-family: $font-family;
    font-weight: 400;
    font-size: 12px;
    line-height: 117%;
    color: $color-font-second;
    position: absolute;
    left: 8px;
  }

  &__body {
    display: flex;
    align-items: center;
  }
  &__field {
    font-family: $font-family;
    font-weight: 400;
    font-size: 14px;
    line-height: 114%;
    color: #5a5a5a;
    border: 1px solid $color-border;
    border-radius: 10px;
    padding: 9px 7px 9px 25px;
    width: 100%;

    &:focus {
      border: 1px solid $color-brand-two;
      transition:
        border,
        left 0.5s;

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
