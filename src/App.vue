<template>
  <div id="app" ref="app">
    <h1></h1>
    <navbar />
    <section_1 />
    <section_2 />
    <section_3 />
    <section_4 />
    <section_footer />
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
import section_4 from "@/components/section_4--icons";
import section_footer from "@/components/section_5--footer";

import buttonAnimation from "@/scripts/button";

Vue.use(BootstrapVue);

export default {
  name: "App",
  components: {
    navbar,
    section_1,
    section_2,
    section_3,
    section_4,
    section_footer,
  },
  mounted() {
    buttonAnimation();
    this.createShine();
  },
  methods: {
    createShine() {
      const mainContainer = this.$refs.app;

      for (let i = 1; i <= 4; i++) {
        const circle = document.createElement("div");

        circle.className = `circle circle_${i}`;
        mainContainer.prepend(circle);
      }
    },
  },
};
</script>

<style lang="less">
body {
  color: @color-white;
  background: @color-dark-blue;
  font-size: 16px;
  font-family: "Inter", sans-serif;
  font-weight: 400;
  overflow-x: hidden;

  .logo {
    max-width: 170px;
    width: 100%;
  }

  .text-content {
    display: flex;

    &:before {
      content: "";
      display: block;
      width: 20px;
      height: 20px;
      margin-right: 10px;
      margin-top: 0.1em;
      flex-shrink: 0;
    }

    &.phone:before {
      background: url("data:image/svg+xml,%3Csvg width='16' height='16' viewBox='0 0 16 16' fill='none' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath d='M5.8281 5.78793C5.11267 6.39582 4.8505 7.50447 5.46825 8.39388C6.04632 9.22617 6.7745 9.95419 7.6066 10.532C8.49604 11.1496 9.60464 10.8874 10.2125 10.1719L10.2192 10.1751C10.9956 10.5347 11.8203 10.7812 12.6667 10.9068V12.6667L12.6659 12.6667L12.664 12.6667C7.34768 12.6742 3.32765 8.60741 3.33334 3.33573V3.33333H5.09291L5.09303 3.33411C5.21866 4.18043 5.46507 5.00436 5.82476 5.78072L5.8281 5.78793ZM12.6659 14H13.3333C13.7015 14 14 13.7015 14 13.3333V10.3318C14 10.0014 13.758 9.72087 13.4312 9.67237L12.8618 9.58786C12.1415 9.48097 11.4404 9.27128 10.7797 8.96523L10.2778 8.73273C9.98692 8.598 9.64136 8.68933 9.45505 8.95017L9.22784 9.26829C9.0287 9.54709 8.64852 9.63224 8.3671 9.43682C7.66557 8.94968 7.05071 8.33495 6.56335 7.63326C6.36788 7.35183 6.45304 6.97158 6.73189 6.77244L7.04985 6.54538C7.31073 6.35907 7.40207 6.01347 7.26731 5.7226L7.03456 5.22022C6.72849 4.5596 6.51882 3.8585 6.41191 3.13833L6.32736 2.56877C6.27884 2.24197 5.9983 2 5.66792 2H2.66667C2.29848 2 2.00001 2.29848 2.00001 2.66667V3.33429C1.99353 9.33858 6.60682 14.0086 12.6659 14Z' fill='%23FF7C00'/%3E%3C/svg%3E%0A")
        center / contain no-repeat;
    }
    &.mail:before {
      background: url("data:image/svg+xml,%3Csvg width='16' height='16' viewBox='0 0 16 16' fill='none' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath d='M13.3335 13.3334H2.66683C1.93045 13.3334 1.3335 12.7364 1.3335 12V3.94202C1.36457 3.22839 1.95252 2.66601 2.66683 2.66669H13.3335C14.0699 2.66669 14.6668 3.26364 14.6668 4.00002V12C14.6668 12.7364 14.0699 13.3334 13.3335 13.3334ZM2.66683 5.24535V12H13.3335V5.24535L8.00016 8.80002L2.66683 5.24535ZM3.20016 4.00002L8.00016 7.20002L12.8002 4.00002H3.20016Z' fill='%23FF7C00'/%3E%3C/svg%3E%0A")
        center / contain no-repeat;
    }
    &.address:before {
      background: url("data:image/svg+xml,%3Csvg width='16' height='16' viewBox='0 0 16 16' fill='none' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath d='M8.00016 14C7.15812 13.2818 6.37762 12.4944 5.66683 11.646C4.60016 10.372 3.3335 8.4747 3.3335 6.6667C3.33255 4.7784 4.46966 3.07563 6.21421 2.35297C7.95876 1.6303 9.96687 2.03019 11.3015 3.36603C12.1791 4.23977 12.6708 5.42829 12.6669 6.6667C12.6669 8.4747 11.4002 10.372 10.3335 11.646C9.62271 12.4944 8.84221 13.2818 8.00016 14ZM8.00016 3.33337C6.16013 3.33557 4.66903 4.82666 4.66683 6.6667C4.66683 7.44403 5.01816 8.79003 6.69016 10.7907C7.10226 11.2827 7.53951 11.7531 8.00016 12.2C8.46086 11.7537 8.89832 11.2839 9.31083 10.7927C10.9822 8.78937 11.3335 7.44337 11.3335 6.6667C11.3313 4.82666 9.8402 3.33557 8.00016 3.33337ZM8.00016 8.6667C6.89559 8.6667 6.00016 7.77127 6.00016 6.6667C6.00016 5.56213 6.89559 4.6667 8.00016 4.6667C9.10473 4.6667 10.0002 5.56213 10.0002 6.6667C10.0002 7.19713 9.78945 7.70584 9.41438 8.08091C9.0393 8.45599 8.5306 8.6667 8.00016 8.6667Z' fill='%23FF7C00'/%3E%3C/svg%3E%0A")
        center / contain no-repeat;
    }
    &.time:before {
      background: url("data:image/svg+xml,%3Csvg width='16' height='16' viewBox='0 0 16 16' fill='none' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath d='M8.00016 14.6666C4.31826 14.6666 1.3335 11.6818 1.3335 7.99992C1.3335 4.31802 4.31826 1.33325 8.00016 1.33325C11.6821 1.33325 14.6668 4.31802 14.6668 7.99992C14.6628 11.6801 11.6804 14.6625 8.00016 14.6666ZM8.00016 2.66659C5.05464 2.66659 2.66683 5.0544 2.66683 7.99992C2.66683 10.9454 5.05464 13.3333 8.00016 13.3333C10.9457 13.3333 13.3335 10.9454 13.3335 7.99992C13.3302 5.05577 10.9443 2.66989 8.00016 2.66659ZM11.3335 8.66659H7.3335V4.66659H8.66683V7.33325H11.3335V8.66659Z' fill='%23FF7C00'/%3E%3C/svg%3E%0A")
        center / contain no-repeat;
    }
  }

  fieldset {
    padding: 0 !important;
  }
}
@import "https://cdnjs.cloudflare.com/ajax/libs/normalize/8.0.1/normalize.min.css";
@import "./styles/variables.less";
@import "./styles/grid.less";
@import "./styles/normalize.less";
@import "./styles/font.less";
@import "./styles/button.less";
@import "./styles/background.less";
@import "./styles/media_tab.less";
@import "./styles/media_tab-rotate.less";
@import "./styles/media_mob.less";
</style>
