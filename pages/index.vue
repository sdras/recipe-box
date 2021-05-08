<template>
  <main>
    <base-hero />

    <BaseSearchInput />

    <section>
      <div class="recipe-piece">
        <div v-for="recipe of recipes" :key="recipe.slug">
          <NuxtLink
            :to="{ name: 'recipes-slug', params: { slug: recipe.slug } }"
          >
            <img :src="recipe.img" class="recipe-list-img" />
            <div>
              <h2>{{ recipe.title }}</h2>
              <p>by {{ recipe.author.name }}</p>
              <p>{{ recipe.description }}</p>
            </div>
          </NuxtLink>
        </div>
      </div>
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
  width: 100%;
}

section {
  padding: 50px;
  display: flex;
  justify-content: center;
}

section div {
  max-width: 1000px;
}

.recipe-piece {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  grid-column-gap: 50px;
  grid-row-gap: 50px;
}
</style>
