<template>
  <v-app-bar app color="black" dark>
    <v-app-bar-nav-icon @click="toggleDrawer"></v-app-bar-nav-icon>
    <v-toolbar-title>My Events</v-toolbar-title>
    <v-spacer></v-spacer>
    <v-menu offset-y>
      <template v-slot:activator="{ on, attrs }">
        <v-btn text @click="navigateTo('/nosotros')">Nosotros</v-btn>
        <v-btn text @click="navigateTo('/eventos')">Eventos</v-btn>
        <v-btn text @click="navigateTo('/blog')">Blog</v-btn>
        <v-btn text @click="navigateTo('/agenda')">Agenda</v-btn>
        <v-btn text @click="navigateTo('/contacto')">Contacto</v-btn>
        <v-btn text @click="navigateTo('/tienda')">Tienda</v-btn>
      </template>
      <v-list>
        <v-list-item @click="navigateTo('create')">Crea tu evento</v-list-item>
        <v-list-item @click="navigateTo('about')">Quiénes somos</v-list-item>
        <v-list-item @click="navigateTo('advisor')">Tu asesor</v-list-item>
      </v-list>
    </v-menu>
    <v-text-field
      v-model="search"
      append-icon="mdi-magnify"
      label="Buscar"
      single-line
      hide-details
    ></v-text-field>
  </v-app-bar>
</template>

<script setup>
import { ref } from "vue";
import { useRouter } from "vue-router";

const search = ref("");
const router = useRouter();
const drawerOpen = ref(false); // Añadido

const toggleDrawer = () => {
  drawerOpen.value = !drawerOpen.value;
};

const navigateTo = (routeName) => {
  router.push(routeName);
};
</script>
