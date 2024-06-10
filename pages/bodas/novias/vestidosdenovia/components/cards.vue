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
          title: "Valenta",
          flex: 4,
          src: "https://lh3.googleusercontent.com/p/AF1QipN9n9O6J3A7_UZnkCayaiffoy232zE9r_Z7HVaf=s680-w680-h510",
          link: "/bodas/novias/vestidosdenovia/valenta", // Añadido coma
          isLiked: false
        },
        {
          title: "Lara Alma",
          flex: 4,
          src: "https://lh3.googleusercontent.com/p/AF1QipMJBHPady5iCvgqeEWlO5erXbLptgvNqUssYL9Q=s680-w680-h510",
          link: "/bodas/novias/Belleza/laraalma", // Añadido coma
          isLiked: false
        },
        {
          title: "Ever After",
          flex: 4,
          src: "https://lh3.googleusercontent.com/p/AF1QipOeieAInXgC-rMTY4ao_2BbPD42s-QIkJaeavBT=s680-w680-h510",
          link: "/bodas/novias/Belleza/everafter", // Añadido coma
          isLiked: false
        },
        {
          title: "Versalles",
          flex: 4,
          src: "https://lh3.googleusercontent.com/p/AF1QipPEn9OwJX4T5HJvNhbmkrmNOBT4nWlalbwVD5QB=s680-w680-h510",
          link: "/bodas/novias/Belleza/versalles", // Añadido coma
          isLiked: false
        },
        {
          title: "Cherry Tree",
          flex: 4,
          src: "https://lh3.googleusercontent.com/p/AF1QipPYiRoXep5aqoxmCWdF9kJMo1pBzCq67D45tIUs=s680-w680-h510",
          link: "/bodas/novias/Belleza/cherrytree", // Añadido coma
          isLiked: false
        },
        {
          title: "Nina Vestidos",
          flex: 4,
          src: "https://lh3.googleusercontent.com/p/AF1QipOOaFVq68Yp0XZB78MomlSX3mrpOlFTpQyGpXII=s680-w680-h510",
          link: "/bodas/novias/Belleza/ninavestidos", // Añadido coma
          isLiked: false
        },
        {
          title: "Casa Blanca Novias",
          flex: 4,
          src: "https://lh3.googleusercontent.com/p/AF1QipO3oD8TBefhTfg4-siJHrI-tBeBXdzXQscqJ25w=s680-w680-h510",
          link: "/bodas/novias/Belleza/casablancanovias", // Añadido coma
          isLiked: false
        },
        {
          title: "The Bridal Store",
          flex: 4,
          src: "https://scontent.flpb2-1.fna.fbcdn.net/v/t1.6435-9/32956691_439072076520147_959678328820727808_n.jpg?_nc_cat=109&ccb=1-7&_nc_sid=5f2048&_nc_ohc=GJrUvjp8Bn4Q7kNvgGir5LQ&_nc_ht=scontent.flpb2-1.fna&oh=00_AYCHF_Bb2jlW9ypZ-6JCsvefvKCM4iJdsiCLspTYqcLR2Q&oe=668E95A1",
          link: "/bodas/novias/Belleza/thebridalstore", // Añadido coma
          isLiked: false
        },
        {
          title: "Esposa Bella",
          flex: 4,
          src: "https://scontent.flpb2-2.fna.fbcdn.net/v/t39.30808-6/365468157_833712505114985_1719430984537631168_n.jpg?_nc_cat=103&ccb=1-7&_nc_sid=5f2048&_nc_ohc=voqtS6YuTv4Q7kNvgG3LR8G&_nc_ht=scontent.flpb2-2.fna&oh=00_AYCc4V4pz0IUZFdQwDTxpEInKpuyEzN_lJoCowYlLnyShg&oe=666CEEA9",
          link: "/bodas/novias/Belleza/esposabella",
          isLiked: false
        },
        {
          title: "Arte Novia",
          flex: 4,
          src: "https://lh3.googleusercontent.com/p/AF1QipM-9eG3QCutDHEEpm9Jd5gM0srMXnoR4F4WUprd=s680-w680-h510",
          link: "/bodas/novias/Belleza/artenovia",
          isLiked: false
        },
        {
          title: "Le Fior",
          flex: 4,
          src: "https://i.pinimg.com/564x/93/49/7f/93497f3a960a9ce1bdd0975976f8cba9.jpg",
          link: "/bodas/novias/Belleza/lefior",
          isLiked: false
        },
        {
          title: "Reuniones",
          flex: 4,
          src: "https://i.pinimg.com/564x/bc/98/a1/bc98a1ef38f046eec57e2bfbfe50b080.jpg",
          link: "/bodas", // Añadido coma
          isLiked: false
        },
        {
          title: "Pasteles",
          flex: 4,
          src: "https://img.freepik.com/foto-gratis/dulces-postres-boda_1303-10559.jpg?t=st=1717657284~exp=1717660884~hmac=4349d78c1b1a29e60d5d5706de0e923c0a242519116024cc1c895c47ea53c54f&w=740",
          link: "/pasteles", // Añadido coma
          isLiked: false
        },
        {
          title: "Flores",
          flex: 4,
          src: "https://i.pinimg.com/564x/48/7a/a3/487aa331b31ae0a0293a31afd28ab646.jpg",
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
