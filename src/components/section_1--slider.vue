<template>
  <section class="section section_1--slider">
    <div class="grid">
      <b-carousel
        id="carousel"
        v-model="slide"
        :interval="5000"
        controls
        indicators
        @sliding-end="onSlideEnd"
      >
        <b-carousel-slide>
          <h2 class="title text-900">Оптовые продажи запчастей</h2>
          <h4 class="text-orange text">к{{'\xa0'}}автомобилям LADA.</h4>
          <!-- <button class="button text-up text-white text-800">Связаться с нами</button> -->
          <button data-shiny-button class="shiny-button">
            <p class="text-800 title _md">Связаться с{{'\xa0'}}нами</p>
            <canvas></canvas>
          </button>
          <img
            class="image"
            src="../assets/slider_1.png"
            alt="Изображение запчастей"
          />
        </b-carousel-slide>

        <b-carousel-slide>
          <h2 class="title text-900">Нас рекомендуют</h2>
          <h4 class="text-orange text">как надёжного партнёра!</h4>
          <button data-shiny-button class="shiny-button">
            <p class="text-800 title _md">Рекомендации</p>
            <canvas></canvas>
          </button>
          <img
            class="image"
            src="../assets/slider_2.png"
            alt="Изображение запчастей"
          />
        </b-carousel-slide>

        <b-carousel-slide>
          <h2 class="title text-900">Гибкие цены и{{'\xa0'}}индивидуальный подход!</h2>
          <h4 class="text-orange text">Довольные клиенты с{{'\xa0'}}2013{{'\xa0'}}года.</h4>
          <button data-shiny-button class="shiny-button">
            <p class="text-800 title _md">Ознакомиться с прайсом</p>
            <canvas></canvas>
          </button>
          <img
            class="image"
            src="../assets/slider_3.png"
            alt="Изображение запчастей"
          />
        </b-carousel-slide>
      </b-carousel>
    </div>
  </section>
</template>

<script>
import buttonAnimation from "@/scripts/button";

export default {
  name: "section_1",
  data() {
    return {
      slide: 0,
      sliding: null,
    };
  },
  methods: {
    onSlideEnd() {
      buttonAnimation();
      this.sliding = false;
    },
  },
};
</script>

<style lang="less">
@import "../styles/variables.less";
@import "../styles/font.less";
@import "../styles/slider.less";

.section_1--slider {
  margin-top: 4em;

  .carousel {
    .carousel-item {
      height: 400px;

      .carousel-caption {
        text-align: left;
        position: static;
        display: grid;
        grid-template-columns: 1.1fr 0.9fr;
        grid-auto-rows: min-content;
        gap: 20px 20px;
        grid-template-areas:
          "title image"
          "text image"
          "button image";
        .title {
          grid-area: title;
        }
        .text {
          grid-area: text;
        }
        .button {
          grid-area: button;
        }
        .image {
          grid-area: image;
        }
      }
    }
    
  }
}
</style>
