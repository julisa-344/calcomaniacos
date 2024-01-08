<template>
  <v-app>
    <HeaderComponents/>
    <v-main>
      <HeroBanner/>
    </v-main>
  </v-app>
</template>

<script>
import HeroBanner from './components/HeroBanner.vue'
import HeaderComponents from './components/HeaderComponents.vue'
export default {
  name: 'App',

  components: {
    HeroBanner,
    HeaderComponents,
  },

  data: () => ({
    //
  }),
}
</script>
<style lang="scss" src="./style/style.scss"></style>
