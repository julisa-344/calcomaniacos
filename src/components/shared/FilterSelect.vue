<template>
    <select v-model="selectedOption">
        <option v-for="option in options" :value="option.value" :key="option.value">{{ option.label }}</option>
    </select>
</template>

<script>
export default {
    name: 'FilterSelect',
    data() {
        return {
            selectedOption: null,
            options: [
                { label: 'ricky and morty', value: 'rick' },
                { label: 'arctic monkey', value: 'arcticmonkey' },
                { label: 'anime', value: 'anime' },
                { label: 'messi', value: 'messi'},
                { label: 'memes', value: 'memes'},
            ]
        };
    }
};
</script>
