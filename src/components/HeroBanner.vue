<template>
  <v-container class="bg-color m-height m-width relative p-4">
      <div class="bg-rainbow">
      </div>
      <div class="bg-rainbowmax">
      </div>
      <v-row class="text-center">
        <v-col cols="12">
          <img class="logo-img" :src="require('../assets/logo.png')" alt="logo">
        </v-col>

        <v-col class="mb-4">
          <h1 class="display-2 font-weight-bold mb-3">
            Calcomaniacos
          </h1>

          <p class="subheading font-weight-regular">
            Locos por los
            <br>stickers
          </p>
          <ButtonClassic buttonText="Crear tu colección" />
            <img class="img-sticker" :src="require('../assets/cat.png')" alt="gato">
            <img class="img-sticker-left" :src="require('../assets/dog.png')" alt="gato">
        </v-col>
      </v-row>
    </v-container>
</template>

<script>
import ButtonClassic from './shared/ButtonClassic.vue'
export default {
  name: 'HeroBanner',
  components: {
    ButtonClassic
  }
}
</script>
<style>
.logo-img{
  width: 256px;
  margin-bottom: -5rem;
  margin-top: 2rem;
}
.bg-rainbow{
  background-image: url('../assets/rbm.svg');
  background-repeat: no-repeat;
  height: 300px;
  width: 700px;
  position: absolute;
  top: -30px;
  right: -376px;
}
.bg-rainbowmax{
  background-image: url('../assets/rb.svg');
  background-repeat: no-repeat;
  height: 400px;
  width: 800px;
  position: absolute;
  left: -138px;
  bottom: -58px;
}
.img-sticker{
  width: 400px;
  position: absolute;
  bottom: 50px;
  left: 44px;
}
.img-sticker-left{
  width: 400px;
  position: absolute;
  bottom: -4px;
  right: 44px;
}
</style>