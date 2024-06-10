<template>
  <AppBar></AppBar>
  <Hero></Hero>
  <filters></filters>
  <Cards></Cards>
  <Footer></Footer>
</template>

<script setup>
import { ref } from 'vue';
import AppBar from "./components/app-bar.vue";
import Filters from './components/filters.vue';
import Hero from "./components/hero.vue";
import Cards from "./components/cards.vue";
import Footer from "./components/footer.vue";


</script>
