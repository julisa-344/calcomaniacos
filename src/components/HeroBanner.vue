<template>
  <div class="bg-color m-height m-width absolute bg"></div>
  <v-container class="m-height m-width relative p-4 herobg" :style="{ backgroundImage: `url(${backgroundImageList[backgroundImageIndex]})` }">
    <v-row class="text-center">
      <v-col cols="12">
        <img class="logo-img" :src="require('../assets/logo.png')" alt="logo">
      </v-col>

      <v-col class="mb-4">
        <h1 class="display-2 font-weight-bold mb-3">
          Calcomaniacos
        </h1>

        <p class="subheading font-weight-regular">
          Locos por los stickers
        </p>
        <ButtonClassic buttonText="Crear tu colección" src="#makeCollection"/>
        <br>
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
  },
  data() {
    return {
      backgroundImageIndex: 0,
      backgroundImageList: [
        require('../assets/bg1.png'),
        require('../assets/bg2.png'),
        require('../assets/bg3.png'),
        require('../assets/bg4.png')
      ]
    }
  },
  mounted() {
    setInterval(() => {
      this.backgroundImageIndex = (this.backgroundImageIndex + 1) % this.backgroundImageList.length;
    }, 2500);
  }
}
</script>

<style>
.herobg{
  background-repeat: no-repeat;
  background-size: cover;
  background-position: center;
  height: 100vh;
  width: 100%;
  position: relative;
  transition: background-image 0.5s ease-in-out;
}
.logo-img{
  width: 256px;
  margin-bottom: -5rem;
  margin-top: 2rem;
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
.subheading{
  font-size: 2rem;
  margin-top: 2rem;
  color: #fff;
}
.bg{
  z-index: 0;
  top: o;
  right: 0;
  position: absolute;
  width: 100vw;
}
.arrow-video{
  width: 50px;
}
</style>