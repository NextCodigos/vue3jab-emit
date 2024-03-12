<template>
  <div>
    <h1>Padre:</h1>
    <h2 v-if="showPadre">{{ nombrePadre }}</h2> <!-- Mostrar nombre del padre si showPadre es verdadero -->
    <h2 v-if="showPadre">{{ edadPadre }}</h2> <!-- Mostrar edad del padre si showPadre es verdadero -->
    <h3 v-if="isVisiblemessagePadre">{{ messagePadre }}</h3>
    <button v-on:click="$event => isVisiblemessagePadre = !isVisiblemessagePadre">Toogle Visibility</button>
    <h1>Hijo:</h1>
    <h2>{{ nombre }}</h2>
    <h2>{{ edad }}</h2>
    <button @click="cambiarValoresHijo">Cambiar valores hijo</button>
    <button @click="cambiarValoresPadre">Cambiar valores padre</button>
    <h3 v-if="isVisiblemessageHijo">{{ messageHijo }}</h3>
    <button v-on:click="toggleVisibilityHijo">Toogle Visibility</button>
  </div>
</template>

<script setup>
import { ref } from 'vue';
// Código JavaScript del componente

// Definir variable reactiva para el nombre del hijo
const nombre = ref('JAB');

// Definir variable reactiva para la edad del hijo
const edad = ref(18);

// Definir variable reactiva para el nombre del padre
const nombrePadre = ref('Nombre inicial padre');

// Definir variable reactiva para la edad del padre
const edadPadre = ref(30);

// Definir variable reactiva para controlar la visibilidad del padre
const showPadre = ref(true);

// Definir variable reactiva para controlar la visibilidad del hijo
const showHijo = ref(true);

// Función para cambiar los valores del hijo
const cambiarValoresHijo = () => {
  // Cambiar nombre del hijo
  nombre.value = nombre.value === 'JAB' ? 'Nuevo nombre hijo' : 'JAB';

  // Cambiar edad del hijo
  edad.value = edad.value === 18 ? 20 : 18;

  // Alternar visibilidad del hijo
  showHijo.value = !showHijo.value;
};

// Función para cambiar los valores del padre
const cambiarValoresPadre = () => {
  // Cambiar nombre del padre
  nombrePadre.value = nombrePadre.value === 'Nombre inicial padre' ? 'Nuevo nombre padre' : 'Nombre inicial padre';

  // Cambiar edad del padre
  edadPadre.value = edadPadre.value === 30 ? 35 : 30;

  // Siempre establecer showPadre como verdadero al cambiar los valores del padre
  showPadre.value = true;
};
const messagePadre = ref('initial value Padre');
const messageHijo = ref('initial value Hijo');


// Definir variable reactiva para controlar la visibilidad del padre
const isVisiblemessagePadre = ref(true);

// Definir variable reactiva para controlar la visibilidad del hijo
const isVisiblemessageHijo = ref(true);

// Función para alternar la visibilidad del mensaje del hijo
const toggleVisibilityHijo = () => {
  isVisiblemessageHijo.value = !isVisiblemessageHijo.value;
};


// Código listo para ser utilizado

// Cambiar nombre del hijo:

// La línea nombre.value === 'JAB' comprueba si el valor actual de la variable nombre es igual a "JAB".
// Si es verdadero, el valor de nombre se cambia a "Nuevo nombre hijo".
// Si es falso, el valor de nombre se cambia a "JAB".
// En resumen, esta línea cambia el nombre del hijo entre "JAB" y "Nuevo nombre hijo" cada vez que se llama a la función cambiarValoresHijo.

// 2. Cambiar edad del hijo:

// La línea edad.value === 18 comprueba si el valor actual de la variable edad es igual a 18.
// Si es verdadero, el valor de edad se cambia a 20.
// Si es falso, el valor de edad se cambia a 18.
// En resumen, esta línea cambia la edad del hijo entre 18 y 20 cada vez que se llama a la función cambiarValoresHijo.

// En conjunto, estas dos líneas de código se encargan de cambiar los valores del hijo(nombre y edad) cada vez que se pulsa el botón "Cambiar valores hijo".

//   Ejemplo:
// Si el nombre actual del hijo es "JAB" y la edad actual es 18, al pulsar el botón:

// El nombre del hijo cambiará a "Nuevo nombre hijo".
// La edad del hijo cambiará a 20.
// Si el nombre actual del hijo es "Nuevo nombre hijo" y la edad actual es 20, al pulsar el botón:

// El nombre del hijo cambiará a "JAB".
// La edad del hijo cambiará a 18.

</script>