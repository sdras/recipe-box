<template>
  <article>
    <h1>{{ recipe.title }}</h1>
    <p>{{ recipe.description }}</p>
    <img :src="`../${recipe.img}`" :alt="recipe.alt" class="recipe-img" />
    <p>Article last updated: {{ formatDate(recipe.updatedAt) }}</p>

    <nuxt-content :document="recipe" />
  </article>
</template>

<script>
export default {
  async asyncData({ $content, params }) {
    const recipe = await $content("recipes", params.slug).fetch();

    return { recipe };
  },
  methods: {
    formatDate(date) {
      const options = { year: "numeric", month: "long", day: "numeric" };
      return new Date(date).toLocaleDateString("en", options);
    }
  }
};
</script>

<style scoped>
.recipe-img {
  width: 300px;
}
</style>
