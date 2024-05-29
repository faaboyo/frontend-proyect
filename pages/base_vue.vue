<template>
    <div>
      <h1>Contador</h1>
      <p>Valor actual: {{ count }}</p>
      <button @click="increment">Incrementar</button><!--@click="increment"**(1)> se puede asignar 1 para enlazar
   -->
      <button @click="decrement">Decrementar</button>


    </div>
  </template>
  
  <script setup>
  // Data
  const count = ref(0); 
  
  // Methods
  const increment = () => { // tambien los signos de llave funcion  () => pueden ser igual a fuction
    count.value++;
  };

  
  const decrement = () => {
    count.value--;
  };
  

  // Computed
  const isEven = computed(() => count.value % 2 === 0);  // vas a guar dar en iseven
  </script>