<template>
    <h2>Crea tu colleción</h2>
    <v-container class="flex bg-color m-width m-height p-4">
        <MainCanvas :cards="selectedCards"/>
        <CardGrid v-on:card-dragged="addCardToCanvas"/>
    </v-container>
</template>

<script>
import CardGrid from './CardGrid.vue';
import MainCanvas from './MainCanvas.vue';
export default {
  components: { CardGrid, MainCanvas },
    name: 'MakeCollection',
    // Opciones del componente aquí
}
</script>

<style scoped>
/* Estilos del componente aquí */
</style>
