<script setup>
import BMenu from './BMenu.vue'
import UButton from '../ui/UButton.vue'
import UInput from '../ui/UInput.vue'
import UHamMenu from '../ui/UHamMenu.vue'
</script>
<template>
  <header class="header">
    <div class="header__logo">
      <a href="#" class="logo__link">
        <img src="@/assets/icn/icn-logo.svg" alt="Логотип сайта" />
        <p class="logo__title">Логотип</p>
      </a>
      <UButton>Купить</UButton>
    </div>

    <UInput placeholder="Поиск по 100 000 товаров" type="text" :search-mod="true"></UInput>
    <BMenu class="header__menu" />
    <UHamMenu class="header__ham-menu" />
  </header>
</template>

<style lang="scss">
.header {
  display: flex;
  gap: 24px;
  flex-direction: row;
  align-items: center;
  justify-content: space-between;
  padding: 12px 0;

  &__logo {
    display: flex;
    align-items: center;
    gap: 32px;

    @media screen and (max-width: 925px) {
      display: none;
    }

    & .button {
      font-family: $second-family;
      font-weight: 500;
      font-size: 14px;
      color: #000;
      padding: 14.5px 23px;
      line-height: normal;
      margin-right: 24px;
    }
  }

  &__menu {
    display: flex;
    flex: 1 0 auto;

    @media screen and (max-width: 1200px) {
      display: none;
    }
  }

  &__ham-menu {
    display: none;
    @media screen and (max-width: 1200px) {
      display: block;
    }
    @media screen and (max-width: 925px) {
      display: none;
    }
  }
}

.logo {
  &__link {
    display: flex;
    align-items: center;
    gap: 8px;
    text-decoration: none;
    color: #000000;
  }

  &__title {
    font-family: $second-family;
    font-weight: 400;
    font-size: 16px;
  }
}
</style>
