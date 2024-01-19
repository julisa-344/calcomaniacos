<template>
  <v-container class="container-stickers">
    <FilterSelect @categorySelected="filterByCategory" />
    <div class="cards-wrapper">
      <v-card v-for="(card, index) in filteredCards" :key="index" draggable="true" @dragstart="dragStart($event, card)"
        class="cards-stickers">
        <v-img :src="card.src" class="card-image"></v-img>
      </v-card>
    </div>
  </v-container>
</template>

<script>
import data from '../data.js';
import FilterSelect from '@/components/shared/FilterSelect.vue';

export default {
  components: {
    FilterSelect,
  },
  data() {
    return {
      cards: data,
      selectedCategory: '',
    };
  },
  computed: {
    filteredCards() {
      if (this.selectedCategory) {
        return this.cards.filter(card => card.category === this.selectedCategory);
      } else {
        return this.cards;
      }
    },
  },
  methods: {
    dragStart(event, card) {
      console.log('dragStart: CARD', card);
      // Verificar que card es un objeto válido
      if (card && typeof card === 'object') {
        // Convertir el objeto card a una cadena JSON
        event.dataTransfer.setData('card', JSON.stringify(card));
        console.log('dragStart: CARD', JSON.stringify(card));
        this.$emit('cardDragged', card);
      } else {
        console.error('Invalid card:', card);
      }
    },
    filterByCategory(category) {
      this.selectedCategory = category;
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