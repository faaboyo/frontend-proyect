<template>
    <v-parallax>  
        <div class="hero-image">
        <div class="hero-text">
          <h1 class="titulo1" >Almanza</h1>
          <p class="subtitulo">Que un dia especial! sea un Disfrute para 
            Todos
          </p>

        </div>
      </div>
    </v-parallax>
    <br>
      </template>
      
      <script setup>
      
      </script>
      <style>

      .titulo1{
        font-size: 300px;
        color: rgba(254, 240, 211, 0.76);
        font-style: italic;
        font-family: "Great Vibes", cursive;
      }
      
      .subtitulo{
        font-size: 35px;
        color: rgba(254, 240, 211, 0.76);
        font-style: italic;
        font-family: "Great Vibes", cursive;
      }

      body, html {
        height: 100%;
        margin: 10px;
      }

      
      .hero-image {
        background-image: linear-gradient(rgba(0, 0, 0, 0.5), rgba(0, 0, 0, 0.5)), url("https://www.palaciodeaviles.com/wp-content/uploads/fly-images/5733/bodas-en-octubre-870x0.jpg");
        height: 100vh;
        background-position: center;
        background-repeat: no-repeat;
        background-size: cover;
        position: relative;
      }
      
      .hero-text {
        text-align: center;
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
        color: white;
      }



      </style>