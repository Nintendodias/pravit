<template>
  <section class="section section_0--menu">
    <div class="grid">
      <b-navbar toggleable="lg">
        <b-navbar-brand href="#">
          <img src="@/assets/logo_white.png" alt="" id="logo" />
        </b-navbar-brand>

        <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

        <b-collapse id="nav-collapse" is-nav>
          <b-navbar-nav>
            <b-nav-item href="#">Оформление заказа</b-nav-item>
            <b-nav-item href="#">Прайс-лист</b-nav-item>
            <b-nav-item href="#">Контакты</b-nav-item>
          </b-navbar-nav>
          <b-navbar-nav class="--social">
            
          </b-navbar-nav>
        </b-collapse>
      </b-navbar>
    </div>
  </section>
</template>

<script>
export default {
  name: "navbar",
};
</script>

<style lang="less">
@import "../styles/variables.less";

.section_0--menu {
  position: fixed;
  top: 0;
  width: 100%;
  padding: 0 !important;
  height: auto;
  z-index: 100;
  background: #1d222f;

  .navbar-brand {
    img {
      max-width: 170px;
      width: 100%;
    }
  }

  #nav-collapse {
    justify-content: flex-end;

    li a {
      color: @color-white;
      padding-left: 1.5rem;
      padding-right: 1.5rem;

      &:hover {
        color: @color-orange;
      }
    }
  }
}
</style>
