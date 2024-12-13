<script setup></script>
<template>
  <header class="header">
    <div class="header__logo">
      <a href="#" class="logo__link">
        <img src="" alt="Логотип сайта" />
        <p class="logo__title">Логотип</p>
      </a>
      <button class="header__button button">Каталог</button>
      <label class="input">
        <!-- <span class="input__label">fewsfew</span> -->
        <!-- <img src="images/icn-search.svg" alt="Логотип сайта" /> -->
        <div class="input__body">
          <input type="text" placeholder="Поиск по 100 000 товаров " class="input__field" />
          <span class="input__righticon"></span>
        </div>
      </label>
    </div>
    <nav class="header__menu menu">
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
  </header>
</template>

<style lang="scss">
.header {
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: space-between;

  &__logo {
    display: flex;
    align-items: center;
  }

  &__button {
    font-family: $second-family;
    font-weight: 500;
    font-size: 14px;
    color: #000000;
    border: 1px solid #73aff4;
    border-radius: 8px;
    padding: 15.25px 23px;
    background-color: white;

    &:hover {
      background-color: #73aff4;
    }
  }
}
</style>
