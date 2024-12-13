<template>
  <nav class="menu">
    <ul class="menu__list">
      <li class="menu__item">
        <a href="#" class="menu__link">Информация о компании</a>
      </li>
      <li class="menu__item">
        <a href="#" class="menu__link">Контакты</a>
      </li>
      <li class="menu__item">
        <a href="#" class="menu__link">Полезные ссылки</a>
      </li>
    </ul>
  </nav>
</template>

<style lang="scss">
.menu {
  &__list {
    display: flex;
    gap: 20px;
    list-style: none;
  }

  &__link {
    text-decoration: none;
    font-family: $second-family;
    font-weight: 400;
    font-size: 14px;
    color: #393939;

    &:hover {
      color: $color-font-hover;
    }

    &:active {
      color: $color-font-hover;
    }
  }
}
</style>
