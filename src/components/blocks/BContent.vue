<script setup>
import UCard from '../ui/UCard.vue'
</script>
<template>
  <article class="content">
    <UCard
      image="imgCard.svg"
      is-popular="true"
      discount="25%"
      price="5990"
      old-price="5990"
      in-stock="true"
    >
      Полное название товара в несколько строк для вида с обрывом в конце но мы продолжим текст для
      визуализации трех точек
    </UCard>
  </article>
</template>

<style lang="scss"></style>
