<template>
  <div id="app">
    <div class="header-container">
      <h1>🎥 {{ pageTitle }}</h1>
    </div>
    <HomePage />
  </div>
</template>

<script setup>
import { ref, provide } from "vue";
import HomePage from "./view/HomePage.vue";

const pageTitle = ref("Movie Catalogue");

provide("pageTitle", pageTitle);
provide("setPageTitle", (title) => {
  pageTitle.value = title;
});
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
