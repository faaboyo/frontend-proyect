<template>
    <v-footer
    class="bg-bone text-center d-flex flex-column"
    >
      <div>
        <v-btn
          v-for="icon in icons"
          :key="icon"
          :icon="icon"
          class="mx-4"
          variant="text"
        ></v-btn>
      </div>
  
      <div class="pt-0">
        Somos la empresa líder en organización de eventos en Bolivia. Gracias a nuestras alianzas con las mejores y más responsables empresas del país, puedes planificar cualquier tipo de evento o acontecimiento social desde la comodidad de tu hogar.

En MyEvents, nos encargamos de que todo salga increíble en tu día especial. Relájate y disfruta, nosotros nos ocupamos del resto.

¡Síguenos en nuestras redes sociales y descubre cómo podemos hacer de tu evento un momento inolvidable!
      </div>
  
      <v-divider></v-divider>
  
      <div>
        {{ new Date().getFullYear() }} — <strong>Vuetify</strong>
      </div>
    </v-footer>
  </template>

  
  <script>
    export default {
      data: () => ({
        icons: [
          'mdi-facebook',
          'mdi-twitter',
          'mdi-linkedin',
          'mdi-instagram',
        ],
      }),
    }
  </script>

<style scoped>
.bg-bone {
  background-color: #f7edd8b2;
}
</style>