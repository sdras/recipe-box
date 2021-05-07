<template>
  <div>
    <input
      v-model="searchQuery"
      type="search"
      autocomplete="off"
      placeholder="Search Recipes"
    />
    <ul v-if="recipes.length">
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
