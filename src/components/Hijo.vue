<template>
  <div>
    <h1>Padre:</h1>
    <h2>Nombre: {{ nombrePadre }}</h2>
    <h2>Edad: {{ edadPadre }}</h2>
    <h1>Hijo:</h1>
    <h2>Nombre: {{ nombre }}</h2>
    <h2>Edad: {{ edad }}</h2>
    <button @click="cambiarValoresHijo">Cambiar valores hijo</button>
    <button @click="cambiarValoresPadre">Cambiar valores padre</button>
  </div>
</template>

<script setup>
import { ref } from 'vue';

const nombre = ref('JAB');
const edad = ref(18);

const nombrePadre = ref('Nombre inicial padre');
const edadPadre = ref(30);

const cambiarValoresHijo = () => {
  nombre.value = 'Nuevo nombre hijo';
  edad.value = 20;
};

const cambiarValoresPadre = () => {
  nombrePadre.value = 'Nuevo nombre padre';
  edadPadre.value = 40;
};
</script>
