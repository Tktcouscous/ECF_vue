<template>
  <div id="app">
    <div class="page-wrapper">
      <HeaderComponent />
      <router-view />
      <FooterComponent />
    </div>
  </div>
</template>

<script>
import HeaderComponent from "@/components/Header.vue";
import FooterComponent from "@/components/Footer.vue";

export default {
  name: "App",
  components: {
    HeaderComponent,
    FooterComponent,
  },
};
</script>

<style>
@import "./assets/css/main.css";
</style>
