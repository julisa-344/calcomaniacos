<template>
  <v-app>
    <HeaderComponents/>
    <v-main>
      <HeroBanner/>
      <v-container>
          <CardGrid v-on:card-dragged="addCardToCanvas"/>
          <MainCanvas :cards="selectedCards"/>
      </v-container>
    </v-main>
  </v-app>
</template>

<script>
import HeroBanner from './components/HeroBanner.vue'
import HeaderComponents from './components/HeaderComponents.vue'import CardGrid from './components/CardGrid.vue'
import MainCanvas from './components/MainCanvas.vue'

export default {
  name: 'App',

  components: {
    HeroBanner,
    HeaderComponents,
    CardGrid,
    MainCanvas
  },

  data() {
    return {
      selectedCards: []
    }
  },

  methods: {
    addCardToCanvas(card) {
      console.log('addCardToCanvas: CARD', card);
      this.selectedCards.push(card);
    }
  }
}
</script>
<style lang="scss" src="./style/style.scss"></style>
