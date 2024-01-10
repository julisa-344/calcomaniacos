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
      const cardId = event.dataTransfer.getData('card-id');
      this.$emit('add-card', cardId);
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