<template>
  <section class="section section_5--icons">
    <div class="grid">
      <div class="section__content--grid">
        <h3 class="title text-center">Почему покупатели выбирают нас</h3>
        <div class="item-icons icon_1">
          <img src="../assets/icon_1.png" alt="Ассортимент запчастей" class="icon-image" />
          <p class="item-text text-center">
            Большой ассортимент запчастей к{{ "\xa0" }}автомобилям{{
              "\xa0"
            }}ВАЗ
          </p>
        </div>
        <div class="item-icons icon_2">
          <img src="../assets/icon_2.png" alt="Конкурентноспособные цены" class="icon-image" />
          <p class="item-text text-center">
            Конкурентоспособные цены на{{ "\xa0" }}рынке
          </p>
        </div>
        <div class="item-icons icon_3">
          <img src="../assets/icon_3.png" alt="Обработка заказов" class="icon-image" />
          <p class="item-text text-center">Оперативная обработка заказов</p>
        </div>
        <div class="item-icons icon_4">
          <img src="../assets/icon_4.png" alt="Всегда доступные товары" class="icon-image" />
          <p class="item-text text-center">
            Если Вы{{ "\xa0" }}не{{ "\xa0" }}найдете у{{ "\xa0" }}нас{{
              "\xa0"
            }}то, что нужно, мы{{ "\xa0" }}закажем у{{ "\xa0" }}производителя
          </p>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
    name: "section_5"
}
</script>

<style lang="less">
.section_5--icons {
  .section__content--grid {
    grid-template-columns: repeat(4, 1fr);
    grid-auto-rows: min-content;
    grid-template-areas:
      "title title title title"
      "icon_1 icon_2 icon_3 icon_4";

    .title {
      grid-area: title;
      margin-bottom: 1em;
    }
    .icon_1 {
      grid-area: icon_1;
    }
    .icon_2 {
      grid-area: icon_2;
    }
    .icon_3 {
      grid-area: icon_3;
    }
    .icon_4 {
      grid-area: icon_4;
    }
  }
  .item-icons {
      .icon-image {
          margin: 0 auto;
          margin-bottom: 2em;
      }
  }
}
</style>
