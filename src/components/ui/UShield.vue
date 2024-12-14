<script setup></script>

<template>
  <div class="shield">
    <slot></slot>
  </div>
</template>

<style lang="scss">
.shield {
  display: flex;
  align-items: center;
  justify-content: center;
  background-color: $color-brand;
  border-radius: 4px;
  padding: 6px 10px;
  font-family: $font-family;
  font-weight: 700;
  font-size: 14px;
  line-height: 100%;
  text-align: right;
  color: $color-white;
}
</style>
