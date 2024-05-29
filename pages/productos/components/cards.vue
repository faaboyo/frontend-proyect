<template>
    <v-card
      class="mx-auto"
      max-width="500"
    >
      <v-container fluid>
        <v-row dense>
          <v-col
            v-for="card in cards"
            :key="card.title"
            :cols="card.flex"
          >
            <v-card>
              <v-img
                :src="card.src"
                class="align-end"
                gradient="to bottom, rgba(0,0,0,.1), rgba(0,0,0,.5)"
                height="200px"
                cover
              >
                <v-card-title class="text-white" v-text="card.title"></v-card-title>
              </v-img>
  
              <v-card-actions>
                <v-spacer></v-spacer>
  
                <v-btn
                  color="medium-emphasis"
                  icon="mdi-heart"
                  size="small"
                ></v-btn>
  
                <v-btn
                  color="medium-emphasis"
                  icon="mdi-bookmark"
                  size="small"
                ></v-btn>
  
                <v-btn
                  color="medium-emphasis"
                  icon="mdi-share-variant"
                  size="small"
                ></v-btn>
              </v-card-actions>
            </v-card>
          </v-col>
        </v-row>
      </v-container>
    </v-card>
  </template>

<script>
export default {
  data() {
    return {
      cards: [
        {
          title: 'Card 1',
          flex: 4,
          src: 'https://media.admagazine.com/photos/641239e4d3f4fe9a251b2477/16:9/w_1600,c_limit/destinos-para-bodas.jpg"',
        },
        {
          title: 'Card 2',
          flex: 4,
          src: 'ruta/a/la/imagen2.jpg',
        },
        {
          title: 'Card 3',
          flex: 4,
          src: 'ruta/a/la/imagen3.jpg',
        },
        // Agrega más tarjetas aquí
      ],
    };
  },
};
</script>