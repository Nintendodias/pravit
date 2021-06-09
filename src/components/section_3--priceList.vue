<template>
  <section class="section section_3--priceList">
    <div class="grid">
      <div class="section__content--grid">
        <h3 class="text-center title-priceList title">
          Ознакомиться с{{ "\xa0" }}нашим прайс-листом
        </h3>

        <img src="../assets/priceList.png" alt="" class="img-priceList image" />
        <a href="#" class="text-center text-priceList pdf"
          >Скачать в{{ "\xa0" }}PDF</a
        >
        <a href="#" class="text-center text-priceList xls"
          >Скачать в{{ "\xa0" }}Excel</a
        >
        <div class="form-priceList form">
          <p class="title _lg text-800 text-center">Получить на почту</p>
          <b-form @submit.prevent="onSubmit">
            <b-form-group id="group-name" label="" label-for="name">
              <b-form-input
                id="name"
                v-model="form.name"
                placeholder="Введите ФИО"
                required
              ></b-form-input>
            </b-form-group>

            <b-form-group
              id="group-email"
              label=""
              label-for="email"
              description="Мы никому не передадим Ваши данные"
            >
              <b-form-input
                id="email"
                v-model="form.email"
                type="email"
                placeholder="asd@asd.com"
                required
              ></b-form-input>
            </b-form-group>

            <b-form-group id="group-personal_data_2">
              <b-form-checkbox-group
                v-model="form.checked"
                id="security"
                required
              >
                <b-form-checkbox value="security"
                  ><span class="title _sm"
                    >Нажимая на кнопку, я даю согласие на обработку
                    <a>персональных данных</a></span
                  >
                </b-form-checkbox>
              </b-form-checkbox-group>
            </b-form-group>

            <b-button type="submit" data-shiny-button class="shiny-button">
              <p class="text-800 title _md">Получить прайс-лист</p>
              <canvas></canvas>
            </b-button>
          </b-form>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "section_3",
  data() {
    return {
      form: {
        email: "",
        name: "",
        checked: [],
      },
    };
  },
  methods: {
    onSubmit() {
      console.log(JSON.stringify(this.form));
    },
  },
};
</script>
<style lang="less">
@import "../styles/variables.less";
.section_3--priceList {
  .section__content--grid {
    grid-template-columns: 1fr 1fr 2fr;
    grid-auto-rows: min-content;
    grid-template-areas:
      "title title title"
      "image image form"
      "pdf xls form";

    .title {
      grid-area: title;
    }
    .image {
      grid-area: image;
    }
    .pdf {
      grid-area: pdf;
    }
    .xls {
      grid-area: xls;
    }
    .form {
      grid-area: form;
      background: linear-gradient(223.4deg, #272e3f -15.8%, #3b455e 285.79%);
      border-radius: 4px;
      box-shadow: 0 0 10px #1b212d;
      padding: 10%;

      button {
        max-width: 100%;
        width: 100%;
        margin-top: 1em;

        p {
          color: #000;
        }
      }
      .form-group {
        padding: 0;
      }
      .form-control {
        margin-bottom: 1em;
        padding: 0.7rem 0.75rem;

        &:focus {
            border-color: @color-orange; 
            box-shadow: 0 0 0 0.25rem @color-orange;
        }
      }
      .custom-checkbox {
        display: flex;
        align-items: flex-start;

        input {
          margin-top: 2px;
          margin-right: 1em;
          width: 20px;
          height: 20px;
        }
      }
    }
  }
  .title-priceList {
    margin-bottom: 1em;
  }
  .img-priceList {
    margin: 0 auto;
    max-width: 300px;
    width: 100%;
  }
  .text-priceList {
    display: flex;
    align-items: center;
    justify-content: center;

    &:before {
      content: "";
      display: block;
      width: 40px;
      height: 40px;
      flex-shrink: 0;
      margin-right: 1em;
    }

    &.pdf:before {
      background: url(../assets/pdf_icon.svg) center / contain no-repeat;
    }
    &.xls:before {
      background: url(../assets/xls_icon.svg) center / contain no-repeat;
    }
  }
}
</style>
