<template>
  <v-card
    v-for="(card, index) in cards"
    :key="index"
    draggable="true"
    @dragStop="dragStart(card)"
  >
    <v-img :src="card.image" class="card-image"></v-img>
  </v-card>
</template>

<script>
export default {
  data() {
    return {
      cards: [
        { image: require('../assets/stickers/sticker1.png') },
        { image: require('../assets/stickers/sticker2.jpg') },
        // add more cards as needed
      ],
    };
  },
  methods: {
    dragStart(card) {
      this.$emit('cardDragged', card);
    },
  },
  emits: ['cardDragged'],
};
</script>

<style scoped>
.card-image {
  width: 250px;
  height: 250px;
}
</style>