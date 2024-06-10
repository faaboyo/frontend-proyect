<!-- ContactInfo.vue -->
<template>
  <v-container class="contact-info">
    <v-row>
      <v-col>
        <h2>My Events Company</h2>
        <p><strong>En MyEvents, </strong> nos dedicamos exclusivamente a ayudarte a organizar cada detalle de tu evento. Contamos con toda la logística necesaria para apoyarte en todo lo que necesites. Desde utensilios hasta la cotización de salones de eventos, lo tenemos todo en un solo lugar para que no tengas que preocuparte por nada.
        <br><br>
        Gracias a nuestros acuerdos con las mejores empresas del país, garantizamos que tu evento se llevará a cabo de manera eficiente y eficaz. Nuestra plataforma asegura la calidad de los productos y servicios que ofrecemos. Nos encanta tenerte con nosotros y estamos preparando muchas sorpresas más para ti. ¡Organizar tu evento nunca fue tan fácil!</p>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  name: "ContactInfo",
};
</script>

<style scoped>
.contact-info {
  background-color: #f7edd8b2; /* Mismo color de fondo que el footer */
  padding: 35px !important;
  font-family: "Great Vibes", cursive;
}
.contact-info h2 {
  font-size: 36px;
  color: rgb(197, 113, 3);
}
.contact-info p {
  font-size: 35px;
  color: rgb(0, 0, 0);
  text-align: center; /* Centrar el texto del párrafo */
  margin: 0 auto; /* Asegurar que el centrado funcione correctamente */
  width: 80%; /* Ajustar el ancho según necesites */
}
</style>
