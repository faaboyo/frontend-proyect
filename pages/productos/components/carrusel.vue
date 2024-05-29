<template>
  <v-carousel cycle height="600">
    <v-carousel-item
      v-for="item in items"
      :key="item.key"
      :src="item.image"
      cover
    ></v-carousel-item>
  </v-carousel>
</template>

<script setup>
import { ref } from "vue";
const items = ref([
  {
    image:
      "https://media.admagazine.com/photos/641239e4d3f4fe9a251b2477/16:9/w_1600,c_limit/destinos-para-bodas.jpg",
  },
  {
    image:
      "https://r3.abcimg.es/resizer/resizer.php?imagen=https://sevilla.abc.es/estilo/bulevarsur/wp-content/uploads/sites/14/2019/06/tendencias-bodas-2019-p.jpg&nuevoancho=3293&medio=abc.sevilla",
  },
  {
    image:
      "https://sevilla.abc.es/estilo/bulevarsur/wp-content/uploads/2019/06/tendencia-bengalas-bodas-1024x701.jpg",
  },
]);
</script>