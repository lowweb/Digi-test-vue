<template>
  <label class="input">
    <!-- <span class="input__label"><slot name="inputLabel"></slot></span> -->
    <div class="input__body">
      <input
        :type="type"
        :placeholder="placeholder"
        :disabled="disabled"
        v-model="value"
        class="input__field"
      />
      <IconSearch class="input__icon-search" />
      <Transition name="slide-fade">
        <div class="input__search-options" v-if="value">
          <IconCloseButton class="input__close-button" />
          <UButton class="input__search-button button--fill">Найти</UButton>
        </div>
      </Transition>
    </div>
  </label>
</template>

<script setup>
import IconSearch from '../icons/IconSearch.vue'
import IconCloseButton from '../icons/IconCloseButton.vue'
import UButton from '../ui/UButton.vue'
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

  &__search-button {
    font-family: $font-family;
    font-weight: 400;
    font-size: 16px;
    border-radius: 8px;
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

  &__search-options {
    position: absolute;
    right: 4px;
    display: flex;
    align-items: center;
    gap: 8px;
  }

  &__close-button {
    fill: #333333;
  }
  &__close-button:hover {
    fill: tomato;
  }
}

.slide-fade-enter-active {
  transition: all 0.3s ease-out;
}

.slide-fade-leave-active {
  transition: all 0.8s cubic-bezier(1, 0.5, 0.8, 1);
}

.slide-fade-enter-from,
.slide-fade-leave-to {
  transform: translateX(-3px);
  opacity: 0;
}
</style>
