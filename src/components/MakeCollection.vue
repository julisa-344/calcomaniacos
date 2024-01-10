<template>
    <v-container class="max-height bg-color m-width">
        <h2 class="text-center sub-title">Crea tu colleción</h2>
        <v-container class="flex">
            <MainCanvas :cards="selectedCards"/>
            <CardGrid v-on:card-dragged="addCardToCanvas"/>
        </v-container>
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
