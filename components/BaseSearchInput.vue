<template>
  <div>
    <input
      v-model="searchQuery"
      type="search"
      autocomplete="off"
      id="searchbar"
    />
    <ul v-if="recipes.length" class="search-results">
      <li v-for="recipe of recipes" :key="recipe.slug">
        <NuxtLink :to="{ name: 'recipes-slug', params: { slug: recipe.slug } }">
          {{ recipe.title }}
        </NuxtLink>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      searchQuery: "",
      recipes: []
    };
  },
  watch: {
    async searchQuery(searchQuery) {
      if (!searchQuery) {
        this.recipes = [];
        return;
      }
      this.recipes = await this.$content("recipes")
        .limit(6)
        .search(searchQuery)
        .fetch();
    }
  }
};
</script>

<style scoped>
input {
  padding: 5px 10px;
  border: 1px solid #ccc;
  width: 300px;
}

@media only screen and (max-width: 700px) {
  input {
    width: 60vw;
  }
}

.search-results {
  padding: 20px;
  line-height: 1.4;
}
</style>
