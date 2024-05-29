<template>
    <v-parallax>  
        <div class="hero-image">
        <div class="hero-text">
          <h1 class="titulo1" >My Events</h1>
          <p class="subtitulo">Que un dia especial! sea un Disfrute para 
            Todos
          </p>
          <button class="boton">EMPIEZA</button>
        </div>
      </div>
    </v-parallax>
    <br>
      </template>
      
      <script setup>
      
      </script>
      <style>

      .titulo1{
        font-size: 150px;
        color: rgba(254, 240, 211, 0.76);
        font-style: italic;

      }
      
      .subtitulo{
        font-size: 25px;
        color: rgba(254, 240, 211, 0.76);
        font-style: italic;
      }

      body, html {
        height: 100%;
        margin: 10px;
        font-family:'Times New Roman', Times, serif;
        font-style: italic;
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
      
      .hero-text button {
        border: 10px;
        outline: 0;
        display:inline-block;
        padding: 10px 25px;
        margin: 5%;
        border-radius: 25px;
        border: 2px solid #500303ce;
        color: rgb(245, 210, 210);
        background-color: #4a0808a5;
        text-align: center;
        cursor: pointer;
      }
      
      .hero-text button:hover {
        background-color: #fcbbbb;
        color: rgb(46, 13, 13);
      }
      </style>