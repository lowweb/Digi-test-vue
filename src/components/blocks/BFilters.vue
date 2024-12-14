<script setup>
import UTreeView from '../ui/UTreeView.vue'
import BPriceRange from '../blocks/BPriceRange.vue'
import BCheckBoxGroup from './BCheckBoxGroup.vue'
</script>
<template>
  <aside class="filters">
    <UTreeView />
    <BPriceRange />
    <BCheckBoxGroup :with-search="true" legend="Бренд" />
    <BCheckBoxGroup legend="Размер" />
  </aside>
</template>

<style lang="scss">
.filters {
  min-width: 280px;
  height: 100%;
  display: flex;
  flex-direction: column;
  gap: 28px;
  flex: 0;

  @media screen and (max-width: 925px) {
    display: none;
  }
}
</style>
