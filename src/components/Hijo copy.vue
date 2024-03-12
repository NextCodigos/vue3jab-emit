<template>
  <div>
    <!-- Muestra el título "Hijo" -->
    <h1>Hijo:</h1>
    <!-- Muestra el nombre y edad recibidos como propiedades -->
    <h2>Te llamas {{ nombre }} y tienes {{ edad }} años.</h2>
    <!-- Botón para llamar a la función "enviar" -->
    <button @click="enviar">Cambiar valores</button>
    </div>
</template>

<script setup>
// import HelloWorld from './components/HelloWorld.vue'
// Importa la función "defineEmits" para definir eventos personalizados
const emit = defineEmits(['modificar'])
// Función para emitir el evento "modificar" con nuevos valores
const enviar = () => {
  emit('modificar', 'VUE', 9)
}

// Define las propiedades nombre y edad que este componente espera recibir
const props = defineProps({
  nombre: String,
  edad: Number,
})
</script>

<style scoped></style>