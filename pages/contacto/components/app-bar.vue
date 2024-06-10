<template>
  <v-app-bar app color="black" dark class="barpri">
    <v-app-bar-nav-icon @click="toggleDrawer"></v-app-bar-nav-icon>
    <router-link to="/" class="titulo1p-link">
      <v-toolbar-title class="titulo1p">My Events</v-toolbar-title>
    </router-link>
    <v-spacer></v-spacer>
    <v-menu offset-y>
      <template v-slot:activator="{ on, attrs }">
        <v-btn text @click="navigateTo('/nosotros')" class="font-custom no-uppercase custom-btn">Nosotros</v-btn>
        <v-btn text @click="navigateTo('/contacto')" class="font-custom no-uppercase custom-btn">Contacto</v-btn>
        <v-btn text @click="navigateTo('/tienda')" class="font-custom no-uppercase custom-btn">Tienda</v-btn>
      </template>
    </v-menu>
    <v-text-field
      v-model="search"
      append-icon="mdi-magnify"
      label="Buscar"
      single-line
      hide-details
    ></v-text-field>
    <v-btn icon @click="navigateTo('/carrito')" class="cart-btn">
      <v-icon>mdi-cart</v-icon>
    </v-btn>
  </v-app-bar>

  <v-navigation-drawer
    v-model="drawerOpen"
    :location="$vuetify.display.mobile ? 'bottom' : undefined"
    temporary
    persistent
  >
    <v-list>
      <v-list-item @click="navigateTo('create')" class="font-custom no-uppercase">Crea tu evento</v-list-item>
      <v-list-item @click="navigateTo('advisor')" class="font-custom no-uppercase">Eventos</v-list-item>
      <v-list-item @click="navigateTo('create')" class="font-custom no-uppercase">Agenda</v-list-item>
      <v-list-item @click="navigateTo('about')" class="font-custom no-uppercase">Blog</v-list-item>
      <v-list-item @click="navigateTo('about')" class="font-custom no-uppercase">Quiénes somos</v-list-item>
      <v-list-item @click="navigateTo('advisor')" class="font-custom no-uppercase">Tu asesor</v-list-item>
    </v-list>
  </v-navigation-drawer>
</template>

<script setup>
import { ref } from "vue";
import { useRouter } from "vue-router";

const search = ref("");
const router = useRouter();
const drawerOpen = ref(false); // Variable corregida

const toggleDrawer = () => {
  drawerOpen.value = !drawerOpen.value;
};

const navigateTo = (routeName) => {
  router.push(routeName);
};
</script>

<style scoped>
.titulo1p {
  font-size: 25px;
  text-align: left;
}

.titulo1p-link {
  text-decoration: none; /* Quita el subrayado del enlace */
  cursor: pointer; /* Cambia el cursor a una mano cuando pase por encima */
  color: rgb(250, 252, 147);
}

.barpri {
  font-family: "Great Vibes", cursive;
}

.font-custom {
  font-family: "Playfair Display", serif !important;
}

.no-uppercase {
  text-transform: none !important;
}

.custom-btn {
  font-size: 18px !important; /* Ajusta el tamaño de fuente según sea necesario */
}
</style>
