<script setup>
import BHeader from '@/components/blocks/BHeader.vue'
import BContent from '@/components/blocks/BContent.vue'
import BFilters from './components/blocks/BFilters.vue'
</script>

<template>
  <BHeader />
  <main class="page__main">
    <BFilters />
    <BContent />
  </main>
</template>

<style lang="scss">
* {
  box-sizing: border-box;
}

body {
  padding: 0;
  margin: 0;
  font-family: $font-family, sans-serif;
}

*,
*::before,
*::after {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
  font-weight: normal;
}

.page__body {
  display: flex;
  flex-direction: column;
  min-height: 100vh;
  font-family: $font-family;
  font-size: 14px;
  position: relative;
  padding: 0 100px 36px 100px;

  @media screen and (max-width: 925px) {
    padding: 0 50px 16px 50px;
  }
  @media screen and (max-width: 728px) {
    padding: 0 16px 16px 16px;
  }
}

.page__main {
  display: flex;
  gap: 36px;
}

.page__app {
  display: flex;
  flex-direction: column;
  gap: 24px;
}
</style>
