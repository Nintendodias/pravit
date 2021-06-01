<template>
  <div id="app">
    <navbar />
    <section_1 />
    <section_2 />
    <section_3 />
    <section_5 />
  </div>
</template>

<script>
import Vue from "vue";
import { BootstrapVue } from "bootstrap-vue";
import "bootstrap/dist/css/bootstrap.css";
import "bootstrap-vue/dist/bootstrap-vue.css";

//components
import navbar from "@/components/navbar";
import section_1 from "@/components/section_1--slider";
import section_2 from "@/components/section_2--stages";
import section_3 from "@/components/section_3--priceList";
import section_5 from "@/components/section_5--icons";

import buttonAnimation from "@/scripts/button";

Vue.use(BootstrapVue);

export default {
  name: "App",
  components: {
    navbar,
    section_1,
    section_2,
    section_3,
    section_5
  },
  mounted() {
    buttonAnimation()
  }
};
</script>

<style lang="less">
@import "https://cdnjs.cloudflare.com/ajax/libs/normalize/8.0.1/normalize.min.css";
@import "./styles/variables.less";
@import "./styles/grid.less";
@import "./styles/normalize.less";
@import "./styles/font.less";
@import "./styles/button.less";

body {
  color: @color-white;
  background: @color-dark-blue;
  font-size: 16px;
  font-family: 'Inter', sans-serif;
  font-weight: 400;
}
</style>
