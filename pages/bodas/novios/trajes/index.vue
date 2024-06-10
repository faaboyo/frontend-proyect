<template>
    <AppBar></AppBar>
    <Hero></Hero>

    <filters></filters>
    <Cards></Cards>
    <Footer></Footer>
  </template>
    
  <script setup>
  import AppBar from "./components/app-bar.vue";
  import filters from './components/filters.vue';
  import Hero from "./components/hero.vue";
  import Cards from "./components/cards.vue";
  import Footer from "./components/footer.vue";
  
  const cards = ref([
  {
    title: "Valenta",
    flex: 4,
    src: "https://lh3.googleusercontent.com/p/AF1QipN9n9O6J3A7_UZnkCayaiffoy232zE9r_Z7HVaf=s680-w680-h510",
    category: "Vestidos de Novia",
    price: 5000,
    zone: "Zona 1",
    isLiked: false
  },
  // Añadir más elementos aquí
]);



  </script>
  