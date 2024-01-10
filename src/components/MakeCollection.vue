<template>
    <v-container class="max-height bg-color m-width" id="makeCollection">
        <h2 class="text-center sub-title">Crea tu colleción</h2>
        <v-container class="flex">
            <MainCanvas :cards="cards" @add-card="addCard"/>
            <CardGrid v-on:card-dragged="addCardToCanvas"/>
        </v-container>
    </v-container>
</template>

<script>
import CardGrid from './CardGrid.vue';
import MainCanvas from './MainCanvas.vue';

export default {
  name: 'MakeCollection',
  components: { CardGrid, MainCanvas },
  data() {
    return {
      cards: [], // Define la propiedad "cards"
      canvasCards: [],
    };
  },
  methods: {
    addCard(card) {
      // Verificar que card es un objeto válido
      if (card && typeof card === 'object') {
        this.cards.push(card);
      } else {
        console.error('Invalid card:', card);
      }
    },
    addCardToCanvas(card) {
    // Verificar que card es un objeto válido
    if (card && typeof card === 'object') {
      this.canvasCards.push(card);
    } else {
      console.error('Invalid card:', card);
    }
  },
  },
};
</script>

<style scoped>
</style>
