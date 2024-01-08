<template>
    <v-btn class="button-vuetify m-2" color="white">{{ buttonText }}</v-btn>
</template>

<script>
export default {
    name: 'ButtonClassic',
    props: {
        buttonText: {
            type: String,
            required: true
        }
    }
}
</script>

<style scoped>
.button-vuetify {
   background-color: #fff;
   color: #000;
   padding: 1rem 2rem;
   box-sizing: border-box;
}
</style>
