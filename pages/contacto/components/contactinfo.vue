<!-- ContactInfo.vue -->
<template>
    <v-container class="contact-info">
      <v-row>
        <v-col>
          <h2>Contacto</h2>
          <p><strong>Teléfono:</strong> 63022956</p>
          <p><strong>Horario de Atención:</strong></p>
          <p>Lunes a Viernes: 8am a 16:00</p>
          <p>Sábados: Hasta el mediodía</p>
          <p><strong>Email:</strong> Nos pueden mandar un correo en cualquier momento y le atenderemos a la brevedad.</p>
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
    padding: 40px;
    font-family: "Playfair Display", serif
  }
  .contact-info h2 {
    font-size: 36px;
    color: rgb(197, 113, 3);
  }
  .contact-info p {
    font-size: 20px;
    color: rgb(0, 0, 0);
  }
  </style>
  