<template>
  <main>
    <nav>
      <ul>
        <li v-for="link of recipe.toc" :key="link.id">
          <NuxtLink :to="`#${link.id}`">{{ link.text }}</NuxtLink>
        </li>
      </ul>
    </nav>

    <article>
      <h1 class="recipe-title">{{ recipe.title }}</h1>
      <p>{{ recipe.description }}</p>
      <img :src="`../${recipe.img}`" :alt="recipe.alt" class="recipe-img" />
      <p>Recipe last updated: {{ formatDate(recipe.updatedAt) }}</p>
      <author :author="recipe.author" />

      <nuxt-content :document="recipe" />

      <base-prev-next :prev="prev" :next="next" />
    </article>
  </main>
</template>

<script>
export default {
  async asyncData({ $content, params }) {
    const recipe = await $content("recipes", params.slug).fetch();

    const [prev, next] = await $content("recipes")
      .only(["title", "slug"])
      .sortBy("createdAt", "asc")
      .surround(params.slug)
      .fetch();

    return { recipe, prev, next };
  },
  methods: {
    formatDate(date) {
      const options = { year: "numeric", month: "long", day: "numeric" };
      return new Date(date).toLocaleDateString("en", options);
    }
  }
};
</script>

<style>
.recipe-img {
  width: 300px;
}

h1.recipe-title {
  font-size: 45px;
}

.nuxt-content {
  width: 50vw;
}

.nuxt-content h1 {
  font-size: 28px;
}

.nuxt-content h2 {
  font-size: 28px;
}

.nuxt-content h3 {
  font-size: 22px;
}

.nuxt-content p {
  margin-bottom: 20px;
}

.icon.icon-link {
  background-image: url("~assets/hashtag2.svg");
  display: inline-block;
  width: 20px;
  height: 20px;
  background-size: 20px 20px;
}
</style>
