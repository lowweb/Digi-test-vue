<script setup>
import UCard from '../ui/UCard.vue'
import data from '../../api/data.js'
</script>
<template>
  <section class="content">
    <UCard
      v-for="card in data"
      :key="card.id"
      :image="card.image"
      :is-popular="card.ispopular"
      :discount="card.discount"
      :price="card.price"
      :old-price="card.oldprice"
      :in-stock="card.instock"
    >
      {{ card.caption }}
    </UCard>
  </section>
</template>

<style lang="scss">
.content {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 30px;
  flex-wrap: wrap;

  @media screen and (max-width: 1351px) {
    grid-template-columns: repeat(3, 1fr);
  }

  @media screen and (max-width: 1134px) {
    grid-template-columns: repeat(2, 1fr);
  }

  @media screen and (max-width: 601px) {
    grid-template-columns: repeat(1, 1fr);
    margin: 0 auto;
  }
}
</style>
