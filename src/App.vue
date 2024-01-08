<template>
  <v-app>
    <v-main>
      <HeroBanner/>
    </v-main>
  </v-app>
</template>

<script>
import HeroBanner from './components/HeroBanner.vue'

export default {
  name: 'App',

  components: {
    HeroBanner,
  },

  data: () => ({
    //
  }),
}
</script>
<style lang="scss" src="./style/style.scss"></style>
