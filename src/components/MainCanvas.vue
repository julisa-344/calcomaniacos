<template>
  <div
    class="main-canvas"
    @dragover.prevent
    @drop="handleDrop"
  >
    <v-card
      v-for="(card, index) in cards"
      :key="index"
    >
      <v-img :src="card.image" class="card-image"></v-img>
    </v-card>
  </div>
</template>

<script>
export default {
  props: {
    cards: {
      type: Array,
      default: () => [],
    },
  },
  methods: {
    handleDrop(event) {
      // Obtener los datos transferidos y convertirlos de nuevo a un objeto
      const card = JSON.parse(event.dataTransfer.getData('card'));
      // Emitir un evento al componente padre con la nueva tarjeta
      this.$emit('add-card', card);
    },
  },
};
</script>

<style scoped>
.main-canvas {
  width: 600px;
  height: 75vh;
  background-color: #f5f5f5;
  border: 1px solid #ccc;
  border-radius: 5px;
  padding: 10px;
  margin-bottom: 20px;
}
</style>