<template>
  <v-container class="container-stickers">
    <div class="cards-wrapper">
      <v-card v-for="(card, index) in cards" :key="index" draggable="true" @dragStart="dragStart(card)"
        class="cards-stickers">
        <v-img :src="card.src" class="card-image"></v-img>
      </v-card>
    </div>
  </v-container>
</template>

<script>
import data from '../data.js';

export default {
  data() {
    return {
      cards: data,
    };
  },
  methods: {
    dragStart(event, card) {
    event.dataTransfer.setData('card-id', card.id);
    this.$emit('cardDragged', card);
  },
  },
  emits: ['cardDragged'],
};
</script>

<style scoped>
.container-stickers {
  width: 100%;
  height: 75vh;
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  overflow-y: scroll;
}

.cards-wrapper {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
}
.cards-stickers {
  background-color: transparent;
  cursor: pointer;
}
.card-image {
  width: 200px;
  height: auto;
}
</style>