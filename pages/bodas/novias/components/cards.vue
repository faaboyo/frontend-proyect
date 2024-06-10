<template>
  <v-card max-width="100%">
    <v-container fluid>
      <v-row dense>
        <v-col v-for="card in cards" :key="card.title" :cols="card.flex">
          <v-card>
            <v-img
              :src="card.src"
              class="align-end clickable-image"
              gradient="to bottom, rgba(0,0,0,.1), rgba(0,0,0,.5)"
              height="250px"
              cover
              @click="navigateTo(card.link)"
            >
              <v-card-title
                class="text-white custom-btn"
                v-text="card.title"
              ></v-card-title>
            </v-img>
            <v-card-actions>
              <v-spacer></v-spacer>

              <v-btn
                :color="card.isLiked ? 'red' : 'medium-emphasis'"
                icon="mdi-heart"
                size="small"
                @click.stop="toggleLike(card)"
              ></v-btn>

              <v-btn
                color="isItemSaved(card) ? 'blue' : 'medium-emphasis'"
                icon="mdi-bookmark"
                size="small"
                @click.stop="saveItem(card)"
              ></v-btn>

              <v-btn
                color="medium-emphasis"
                icon="mdi-share-variant"
                size="small"
                @click.stop="share(card)"
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
          title: "Vestidos de Novias",
          flex: 4,
          src: "https://i.pinimg.com/564x/ea/0b/11/ea0b119170dfd9c9299b2ba79f902e49.jpg",
          link: "/bodas/novias/vestidosdenovia", // Añadido coma
          isLiked: false
        },
        {
          title: "Salon de Belleza",
          flex: 4,
          src: "https://i.pinimg.com/564x/bf/c5/61/bfc5616f5fc36b972d57361e7f8effd2.jpg",
          link: "/bodas/novias/Belleza", // Añadido coma
          isLiked: false
        },
        {
          title: "Joyas",
          flex: 4,
          src: "https://i.pinimg.com/564x/c0/61/cc/c061cc42c8bdc29202ec48f99f12d32d.jpg",
          link: "/joyas", // Añadido coma
          isLiked: false
        },
        {
          title: "fiesta de bodas",
          flex: 4,
          src: "https://i.pinimg.com/564x/4e/51/9e/4e519e6cf4377b027085d9c4909867b4.jpg",
          link: "/Fiestabodas", // Añadido coma
          isLiked: false
        },
        {
          title: "Pasteles de Boda",
          flex: 4,
          src: "https://i.pinimg.com/564x/d3/55/2d/d3552d73c348ff7e87f4ff60501aff17.jpg",
          link: "/pasteles", // Añadido coma
          isLiked: false
        },
        {
          title: "Fotografo",
          flex: 4,
          src: "https://i.pinimg.com/564x/69/69/8b/69698ba615610440167c1d956ce90f24.jpg",
          link: "/fotografo", // Añadido coma
          isLiked: false
        },
        {
          title: "Ramos y Flores",
          flex: 4,
          src: "https://i.pinimg.com/564x/8b/cb/ab/8bcbabeaa76fa2693d93ba26179b10a6.jpg",
          link: "/flores", // Añadido coma
          isLiked: false
        },
        {
          title: "Salones de Eventos",
          flex: 4,
          src: "https://i.pinimg.com/564x/b2/b3/b5/b2b3b51fdea6570e9d3a4a1e3c43ee1d.jpg",
          link: "/salonesdeeventos", // Añadido coma
          isLiked: false
        },
        {
          title: "Barman",
          flex: 4,
          src: "https://i.pinimg.com/564x/cf/da/84/cfda84263f91c78eeda9f2f6b4bc3b65.jpg",
          link: "/barman",
          isLiked: false
        },
        {
          title: "Bebidas",
          flex: 4,
          src: "https://i.pinimg.com/564x/a7/ae/72/a7ae7269bcf757664d6837e72b53cc3b.jpg",
          link: "/bebidas",
          isLiked: false
        },
        {
          title: "Catering",
          flex: 4,
          src: "https://i.pinimg.com/564x/93/49/7f/93497f3a960a9ce1bdd0975976f8cba9.jpg",
          link: "/catering",
          isLiked: false
        },
        {
          title: "Comida",
          flex: 4,
          src: "https://i.pinimg.com/564x/ff/94/40/ff944099cfa3072a27f2ed9b913545c3.jpg",
          link: "/comida",
          isLiked: false
        },
        {
          title: "Servicio",
          flex: 4,
          src: "https://i.pinimg.com/564x/b4/5c/8d/b45c8dbda4455709dcfd19268ade2ed6.jpg",
          link: "/servicio",
          isLiked: false
        },
        {
          title: "Show/ Entretenimiento",
          flex: 4,
          src: "https://i.pinimg.com/564x/db/42/df/db42df97b7cb3bc8084162ec9d6e1532.jpg",
          link: "/showentretenimiento",
          isLiked: false
        },
        {
          title: "Grupos",
          flex: 4,
          src: "https://i.pinimg.com/564x/23/a7/52/23a7528241d85336ed9c557614777f17.jpg",
          link: "/grupos",
          isLiked: false
        },
        {
          title: "Amplificacion y Dj",
          flex: 4,
          src: "https://i.pinimg.com/564x/06/45/66/064566333169bb9ad31e7f6e30fcc206.jpg",
          link: "/amplificacion",
          isLiked: false
        },
        {
          title: "Regalos",
          flex: 4,
          src: "https://i.pinimg.com/564x/e4/85/5d/e4855d0c6a261e03a018f74e2c2f177d.jpg",
          link: "/regalos",
          isLiked: false
        },
        {
          title: "Globos",
          flex: 4,
          src: "https://i.pinimg.com/564x/e6/9c/66/e69c66dd823477d0f7f6d6752b66d456.jpg",
          link: "/globos",
          isLiked: false
        },
        {
          title: "Golosinas",
          flex: 4,
          src: "https://i.pinimg.com/736x/4e/f6/7b/4ef67b2ad0302e0085d83ff63f82c663.jpg",
          link: "/golosinas",
          isLiked: false
        },
        {
          title: "Cotillon",
          flex: 4,
          src: "https://i.pinimg.com/564x/77/8a/d3/778ad35951e18b4eece34f073d8cdbae.jpg",
          link: "/cotillon",
          isLiked: false
        },
        {
          title: "Organizador/a de Eventos",
          flex: 4,
          src: "https://i.pinimg.com/564x/5e/7f/7a/5e7f7a57b4cc5dc9b1f82aa90f35b2d6.jpg",
          link: "/organizadordeeventos",
          isLiked: false
        }
        // Agrega más tarjetas aquí
      ],
      shareDialog: false,
      currentCard: null
    };
  },
  methods: {
    navigateTo(link) {
      this.$router.push(link);
    },
    toggleLike(card, event) {
      event.stopPropagation(); // Evita que el clic se propague al `v-img`
      card.isLiked = !card.isLiked;
    },
    saveItem(card, event) {
      event.stopPropagation(); // Evita que el clic se propague al `v-img`
      if (!this.isItemSaved(card)) {
        this.savedItems.push(card);
      } else {
        this.savedItems = this.savedItems.filter(item => item.title !== card.title);
      }
    },
    isItemSaved(card) {
      return this.savedItems.some(item => item.title === card.title);
    },
    share(card, event) {
      event.stopPropagation(); // Evita que el clic se propague al `v-img`
      this.currentCard = card;
      this.shareDialog = true;
    },
    shareOn(platform) {
      console.log(`Compartiendo ${this.currentCard.title} en ${platform}`);
    }
  }
};
</script>

<style scoped>
.text-white {
  font-family: "Great Vibes", cursive;
}

.custom-btn {
  font-size: 35px !important; /* Asegúrate de usar !important */
}

.clickable-image {
  cursor: pointer; /* Cambia el cursor a una mano cuando pase por encima */
}

</style>
