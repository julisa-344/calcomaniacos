<template>
  <div
    class="main-canvas"
    @dragover.prevent
    @drop="handleDrop"
  >
    <v-card
      v-for="(card, index) in cards"
      :key="index"
      :style="{ top: card.y + 'px', left: card.x + 'px' }"
      draggable="true"
      @dragstart="handleDragStart(index, $event)"
      @dragend="handleDragEnd"
    >
      <v-img :src="card.src" class="card-image"></v-img>
      <p>{{ card.src }}</p>
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
    onAddCard: {
      type: Function,
      required: true,
    },
  },
  methods: {
    handleDrop(event) {
      const card = JSON.parse(event.dataTransfer.getData('card') ? event.dataTransfer.getData('card') : null);
      this.onAddCard(card);
    },
    handleDragStart(index, event) {
      event.dataTransfer.setData('text/plain', index);
    },
    handleDragEnd() {
      // Update the card positions after dragging
      const updatedCards = this.cards.map((card, index) => {
        const draggableCard = event.target;
        if (draggableCard.style.top && draggableCard.style.left) {
          card.x = parseInt(draggableCard.style.left);
          card.y = parseInt(draggableCard.style.top);
        }
        return card;
      });
      this.onUpdateCards(updatedCards);
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

.v-card {
  position: absolute;
}
</style>