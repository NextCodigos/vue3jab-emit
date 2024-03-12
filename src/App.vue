<template>
  <div>
    <!-- Muestra el título "Padre" -->
    <h1>Padre:</h1>
    <!-- Llama al componente HijoVue y pasa las propiedades nombre y edad, y maneja el evento modificar -->

    <HijoVue :nombre="nombre" :edad="edad" @modificar="cambiarValor" />

  </div>
</template>

<script setup>
// import HelloWorld from './components/HelloWorld.vue'
import { ref } from 'vue'
import HijoVue from './components/Hijo.vue'

// Función para cambiar el valor de nombre y edad
const cambiarValor = (valor1, valor2) => {
  nombre.value = valor1;
  edad.value = valor2
}

// Define las variables reactivas nombre y edad
const nombre = ref('JAB');
const edad = ref(18);
</script>

<style scoped></style>