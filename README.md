# Digi-test-vue

## 1. Задание
Написать функцию для получения списка всех артикулов товаров в консоли браузера на странице https://groupprice.ru/categories/jenskaya-odejda?referer_from=main_catalog

```sh
function getAllProductIds() {
  const elements = document.querySelectorAll('._product [data-product-id]');
  const productIds = Array.from(elements).map(element => element.getAttribute('data-product-id'));
  return productIds;
  }
  const productIds = getAllProductIds();
  console.log(productIds);
```

## 2. Задание
Написать функцию для получения всех характеристики товара в консоли браузера в виде объекта в формате attributeName: value на странице https://nir-vanna.ru/product/smesitel-bravat-art-f175109c-dlya-rakoviny/

```sh
function getAttributesAndValues() {
  const items = document.querySelectorAll('.tab-pane-product-parameter-item');
  const result = {};
  items.forEach(item => {
    const attributeNameElement = item.querySelector('.parameter-name');
    const valueElement = item.querySelector('.parameter-value');
    if (attributeNameElement && valueElement) {
      const attributeName = attributeNameElement.childNodes[0].textContent.trim();
      const value = valueElement.childNodes[0].textContent.trim();
      result[attributeName] = value;
    }
  });
  return result;
}
const attributesAndValues = getAttributesAndValues();
console.log(attributesAndValues);
```

## Верстка
Клонировать проект в папку, сменить директорию
```sh
git clone https://github.com/lowweb/Digi-test-vue.git
cd Digi-test-vue
```
Установить зависимости
```sh
npm install
```
Запустить сборку в режиме dev
```sh
npm run dev
```
