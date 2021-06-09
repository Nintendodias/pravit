<template>
  <section class="section section_5--footer">
    <iframe
      src="https://yandex.ru/map-widget/v1/?um=constructor%3A7a54f0cdf6b8914a865773a3392cac4b5086b339633132c2f9f1c42314dcf6d3&amp;source=constructor"
      width="100%"
      height="450"
      frameborder="0"
      class="yandex_map"
    ></iframe>

    <footer>
      <div class="grid">
        <div class="section__content--grid">
          <img src="@/assets/logo_white.png" alt="" class="logo" />
          <a href="#" class="title _sm opherta">Договор-оферта</a>
          <a href="#" class="title _sm politic">Политика конфиденциальности</a>
        </div>
      </div>
    </footer>

    <div class="item__absolute">
      <h3 class="title">Контактные данные</h3>
      <div class="line"></div>
      <a href="tel:+79096725085" class="text-800 text-content phone phone_1"
        >+7{{ "\xa0" }}(012){{ "\xa0" }}345-65-89</a
      >
      <a href="tel:+79096725085" class="text-800 text-content phone phone_2"
        >+7{{ "\xa0" }}(012){{ "\xa0" }}345-65-89</a
      >
      <p class="text-content time">
        Пн-Пт, с{{ "\xa0" }}8{{ "\xa0" }}до{{ "\xa0" }}17
      </p>
      <a href="mailto:info@pravit.ru" class="text-content mail"
        >info@pravit.ru</a
      >
      <a
        href="https://yandex.ru/maps/?um=constructor%3A7a54f0cdf6b8914a865773a3392cac4b5086b339633132c2f9f1c42314dcf6d3&source=constructorLink"
        class="text-content address"
        target="_blank"
        >Самарская область, Тольятти, Обводное шоссе,{{ "\xa0" }}71</a
      >
      <button data-shiny-button class="shiny-button button">
        <a
          href="https://yandex.ru/maps/?um=constructor%3A7a54f0cdf6b8914a865773a3392cac4b5086b339633132c2f9f1c42314dcf6d3&source=constructorLink"
          class="text-800 title _md"
          target="_blank"
          >Открыть в&nbsp;навигаторе</a
        >
        <canvas></canvas>
      </button>
    </div>
  </section>
</template>
<script>
export default {
  name: "footer",
};
</script>

<style lang="less">
@import "../styles/variables.less";
.section_5--footer {
  padding-bottom: 1em !important;
  .yandex_map {
    margin-bottom: 10em;
  }

  footer {
    .section__content--grid {
      grid-template-columns: 1fr 2fr 0.5fr 1fr;
      grid-auto-rows: auto;
      grid-template-areas: "logo . opherta politic";
      align-items: center;

      .logo {
        grid-area: logo;
      }
      .opherta {
        grid-area: opherta;
      }
      .politic {
        grid-area: politic;
        margin-top: 0;
      }
    }
  }

  .item__absolute {
    position: absolute;
    background: linear-gradient(223.4deg, #272e3f -15.8%, #3b455e 285.79%);
    border-radius: 4px;
    max-width: 926px;
    height: 351px;
    width: 100%;
    bottom: -5%;
    left: 50%;
    transform: translate(-50%, -30%);
    padding: 3em;
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    grid-auto-rows: auto;
    gap: 20px 10px;
    grid-template-areas:
      "title title title"
      "line line line"
      "phone_1 time address"
      "phone_2 mail button";

    &>.title {
      grid-area: title;
      margin-bottom: 10px;
    }
    &>.line {
      grid-area: line;
    }
    &>.phone_1 {
      grid-area: phone_1;
    }
    &>.phone_2 {
      grid-area: phone_2;
    }
    &>.time {
      grid-area: time;
    }
    &>.mail {
      grid-area: mail;
    }
    &>.address {
      grid-area: address;
    }
    &>.button {
      grid-area: button;
      max-width: 100%;
    }

    .line {
      width: 100%;
      height: 1px;
      background: @color-white;
      margin-bottom: 1em;
    }
    .shiny-button {
      a:hover {
        color: inherit !important;
      }
    }
  }
}
</style>
