<template>
  <main>
    <h1>Recipes</h1>
    <section v-for="recipe of recipes" :key="recipe.slug">
      <NuxtLink :to="{ name: 'blog-slug', params: { slug: recipe.slug } }">
        <img :src="recipe.img" class="recipe-list-img" />
        <div>
          <h2>{{ recipe.title }}</h2>
          <p>by {{ recipe.author.name }}</p>
          <p>{{ recipe.description }}</p>
        </div>
      </NuxtLink>
    </section>
  </main>
</template>

<script>
export default {
  async asyncData({ $content, params }) {
    const recipes = await $content("recipes")
      .only(["title", "description", "img", "slug", "author"])
      .sortBy("createdAt", "asc")
      .fetch();

    return {
      recipes
    };
  }
};
</script>

<style>
.recipe-list-img {
  width: 200px;
}
</style>
