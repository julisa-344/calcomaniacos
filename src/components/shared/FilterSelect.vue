<template>
    <div>
        <select v-model="selectedOption" class="select">
            <option v-for="option in options" :value="option.value" :key="option.value">{{ option.label }}</option>
        </select>
    </div>
</template>

<script>
import data from '@/data.js';

export default {
    name: 'FilterSelect',
    data() {
        return {
            selectedOption: null,
            options: [
                { label: 'ricky and morty', value: 'rickyMorty' },
                { label: 'arctic monkey', value: 'artickMonkeys' },
                { label: 'anime', value: 'anime' },
                { label: 'messi', value: 'messi' },
                { label: 'memes', value: 'memes' },
            ],
            images: data,
        };
    },
    computed: {
        filteredImages() {
            if (this.selectedOption) {
                return this.images.filter(image => image.categoria === this.selectedOption);
            }
            return this.images;
        },
    },
};
</script>

<style>
.select {
    background-color: rgb(188, 188, 188);
}

.image-container {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
}

.image-container img {
    width: 200px;
    height: 200px;
    margin: 10px;
}
</style>