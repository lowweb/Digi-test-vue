<script setup>
import { computed } from 'vue'
import getImageUrl from '@/utils/getImgUrl'

import UButton from './UButton.vue'
import UShield from './UShield.vue'
import IconPopular from '../icons/IconPopular.vue'
const buttonText = computed(() => {
  return props.inStock ? 'Купить' : 'Сообщить о поступлении'
})
const formatPrice = (price) => {
  return price.replace(/\d(?=(\d{3})+$)/g, '$& ')
}
const imgUrl = computed(() => getImageUrl('../assets/images/', props.image))
const props = defineProps({
  isPopular: {
    type: Boolean,
    required: false,
    default: false,
  },
  image: {
    type: String,
    required: false,
    default: '',
  },
  discount: {
    type: String,
    required: false,
    default: '',
  },
  price: {
    type: Number,
    required: false,
    default: null,
  },
  oldPrice: {
    type: Number,
    required: false,
    default: null,
  },
  inStock: {
    type: Boolean,
    required: false,
    default: true,
  },
})
</script>

<template>
  <article class="card">
    <IconPopular v-if="isPopular" class="card__popular" />
    <UShield v-if="discount" class="card__discount">{{ discount }}</UShield>
    <img :src="imgUrl" alt="image-caption" class="card__image" />
    <h2 class="card__title">
      <p class="card__title-sub">Бренд</p>
      <slot></slot>
    </h2>
    <div class="card__price" v-if="inStock">
      {{ formatPrice(price) }} ₽
      <span class="card__price--old">{{ formatPrice(oldPrice) }} ₽</span>
    </div>
    <div class="card__footer">
      <UButton :class="{ 'button--grey': !inStock }">{{ buttonText }}</UButton>
    </div>
  </article>
</template>

<style lang="scss">
.card {
  display: grid;
  grid-template-rows: repeat(max-content, 4);
  gap: 16px;
  max-width: 333px;
  position: relative;

  &__image {
    width: 100%;
    max-height: 200px;
    object-fit: cover;
  }

  &__popular {
    position: absolute;
    top: 12px;
    left: 12px;
  }

  &__discount {
    position: absolute;
    left: 12px;
    top: 162px;
  }

  &__title-sub {
    color: $color-font-second;
    margin-bottom: 8px;
  }
  &__title {
    display: -webkit-box;
    -webkit-line-clamp: 3;
    -webkit-box-orient: vertical;
    overflow: hidden;
    text-overflow: ellipsis;
    font-family: $font-family;
    font-weight: 400;
    font-size: 14px;
    line-height: 114%;
    color: $color-font-main;
  }

  &__price {
    display: flex;
    align-items: center;
    gap: 8px;
    font-family: $font-family;
    font-weight: 700;
    font-size: 16px;
    line-height: 87%;
    color: $color-font-main;

    &--old {
      font-family: $font-family;
      font-weight: 400;
      font-size: 12px;
      line-height: 117%;
      text-decoration: line-through;
      color: $color-font-second;
    }
  }
}
</style>
