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
  return price.toLocaleString('ru-RU')
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
  <article class="card" :class="{ 'card--nostock': inStock === false }">
    <div class="card__body">
      <IconPopular v-if="isPopular" class="card__popular" />
      <UShield v-if="discount" class="card__discount">{{ discount }}</UShield>
      <img
        :src="imgUrl"
        alt="image-caption"
        class="card__image"
        :class="{ 'card__image--noimage': image === '' }"
      />
    </div>
    <h2 class="card__title">
      <p class="card__title-sub">Бренд</p>
      <slot></slot>
    </h2>
    <div class="card__price" v-show="inStock">
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
  grid-template-rows: repeat(4, max-content);
  gap: 16px;
  max-width: 333px;
  position: relative;

  &__body {
    display: flex;
    position: relative;
    overflow: hidden;
  }
  &--nostock {
    grid-template-rows: max-content max-content 1fr;

    & .card__button {
      width: 100%;
    }
  }

  &__image {
    width: 100%;
    max-height: 200px;
    object-fit: cover;
    height: 200px;
    background-color: #f8f8fa;
    transition: 1s;

    &:hover {
      transform: scale(1.2);
      z-index: 1;
    }

    &--noimage::before {
      content: 'no image';
      display: flex;
      align-items: center;
      justify-content: center;
      width: 100%;
      height: 100%;
    }
  }

  &__popular {
    position: absolute;
    top: 12px;
    left: 12px;
    z-index: 3;
  }

  &__discount {
    position: absolute;
    left: 12px;
    top: 162px;
    z-index: 3;
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

  &__footer {
    align-self: flex-end;

    & .button--grey {
      width: 100%;
    }
  }
}
</style>
