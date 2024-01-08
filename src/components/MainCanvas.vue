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
w
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
      console.log(event);
      const cardId = event.dataTransfer.getData('card-id');
      // Emit an event to notify the parent component to add the card to the cards array
      this.$emit('add-card', cardId);
      console.log('wishuwishu', cardId);
    },
  },
};
</script>

<style scoped>
.main-canvas {
  width: 100%;
  height: 100%;
  background-color: #f5f5f5;
  border: 1px solid #ccc;
  border-radius: 5px;
  padding: 10px;
  margin-bottom: 20px;
}
</style>