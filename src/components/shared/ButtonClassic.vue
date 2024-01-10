<template>
    <v-btn class="button-vuetify m-2" color="white" :href="src">{{ buttonText }}</v-btn>
</template>

<script>
export default {
    name: 'ButtonClassic',
    props: {
        buttonText: {
            type: String,
            required: true
        },
        src: {
            type: String,
            required: false
        }
    }
}
</script>

<style scoped>
.button-vuetify {
   background-color: #fff;
   color: #000;
   box-sizing: border-box;
   cursor: pointer;
}
</style>
