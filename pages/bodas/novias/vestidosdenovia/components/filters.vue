<template>
  <v-container class="filtostodo">
    <!-- Filtro de Categoría -->
    <v-select
      v-model="selectedCategory"
      :items="categories"
      label="Categoría"
      multiple
      outlined
      class="custom-select"
    ></v-select>

    <!-- Filtro de Precio -->
    <v-range-slider
      v-model="priceRange"
      :min="minPrice"
      :max="maxPrice"
      :step="100"
      ticks
      tick-size="2"
      color="rgb(197, 113, 3)"
      label="Rango de Precios"
      class="custom-slider"
    >
      <template v-slot:append>
        <div class="range-values">
          {{ priceRange[0] }} - {{ priceRange[1] }}
        </div>
      </template>
    </v-range-slider>

    <!-- Filtro de Zona -->
    <v-autocomplete
      v-model="selectedZone"
      :items="zones"
      label="Zona"
      outlined
      class="custom-autocomplete"
    ></v-autocomplete>

    <!-- Botón de Aplicar Filtros -->
    <v-btn @click="applyFilters" color="rgb(197, 113, 3)" class="custom-btn">Aplicar Filtros</v-btn>
  </v-container>
</template>

<script>
export default {
  data() {
    return {
      selectedCategory: [],
      priceRange: [0, 10000],
      minPrice: 0,
      maxPrice: 10000,
      selectedZone: '',
      categories: ['Vestidos de Novia', 'Juegos Inflables', 'Catering', 'Decoración'],
      zones: ['Zona 1', 'Zona 2', 'Zona 3'],
    };
  },
  methods: {
    applyFilters() {
      this.$emit('filters-applied', {
        selectedCategory: this.selectedCategory,
        priceRange: this.priceRange,
        selectedZone: this.selectedZone,
      });
    },
  },
};
</script>

<style scoped>
.filtostodo {
  outline: 0;
  display: inline-block;
  margin: 2%;
  border-radius: 50%;
  border: 1px solid #ffe8b680;
  color: rgb(197, 113, 3);
  text-align: center;
  line-height: 50px;
  font-family: "Great Vibes", cursive !important;
  font-size: 25px !important;
}

.custom-btn {
  font-size: 25px !important;
  text-transform: none !important; /* Asegura que el texto no se transforme a mayúsculas */
}

.range-values {
  font-size: 20px;
  margin-top: 10px;
  color: rgb(197, 113, 3);
}
</style>
