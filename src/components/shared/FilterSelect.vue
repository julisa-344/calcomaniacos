<template>
  <div>
    <select v-model="selectedCategory" @change="filterByCategory">
      <option value="">All</option>
      <option v-for="category in categories" :value="category" :key="category">
        {{ category }}
      </option>
    </select>
  </div>
</template>

<script>
export default {
  data() {
    return {
      selectedCategory: "",
      categories: [
        "ricky and morty",
        "arctic monkey",
        "anime",
        "messi ",
        "memes",
      ],
    };
  },
  methods: {
    filterByCategory() {
      this.$emit("categorySelected", this.selectedCategory);
    },
  },
};
</script>
<style>
select {
  width: 200px;
  height: 30px;
  border-radius: 5px;
  border: 1px solid #ccc;
  padding: 5px;
  font-size: 16px;
  margin-bottom: 20px;
}
</style>
