<template>
  <v-app>
    <HeaderComponents/>
    <v-main>
      <HeroBanner/>
      <MakeCollection/>
    </v-main>
  </v-app>
</template>

<script>
import HeroBanner from './components/HeroBanner.vue'
import HeaderComponents from './components/HeaderComponents.vue'
import MakeCollection from './components/MakeCollection.vue'

export default {
  name: 'App',

  components: {
    HeroBanner,
    HeaderComponents,
    MakeCollection
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
