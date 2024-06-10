<template>
  <v-carousel cycle height="600" class="imagen">
    <v-carousel-item
      v-for="item in items"
      :key="item.key"
    >
      <v-img
        :src="item.image"
        cover
      ></v-img>
    </v-carousel-item>
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
  {
    image:
      "https://img.freepik.com/foto-gratis/chica-alto-angulo-posando-flores-piso_23-2149861187.jpg?t=st=1717655588~exp=1717659188~hmac=8040ee9db4734dad352468a2a1435b0db5f16ad74466bc2a09b44f0bdef4ff53&w=740",
  },
  {
    image:
      "https://img.freepik.com/foto-gratis/amigos-tintinean-vasos-bebida-bar-moderno_1150-18971.jpg?t=st=1717655286~exp=1717658886~hmac=3ddc52f36aca161463f2ace76a09def06001edf2433525db3420fcab7fab58a2&w=740",
  },
  {
    image:
      " https://img.freepik.com/foto-gratis/tu-mama-horneo-mejor-pastel_329181-7629.jpg?t=st=1717655336~exp=1717658936~hmac=64dbfc3a4ad5a6b441d759a5393a8f4fee54dd261931f9db0e6a345101c07076&w=740",
  },


 
]);
</script>

<style>
      .image {
        background-image: linear-gradient(rgba(0, 0, 0, 0.5), rgba(0, 0, 0, 0.5));
        height: 100vh;
        background-position: center;
        background-repeat: no-repeat;
        background-size: cover;
        position: relative;
      }
</style>