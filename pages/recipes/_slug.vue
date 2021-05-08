<template>
  <main class="single">
    <div class="titlearea">
      <p>{{ formatDate(recipe.createdAt) }}</p>
      <h1 class="recipe-title">{{ recipe.title }}</h1>
      <author :author="recipe.author" />
      <p>{{ recipe.description }}</p>
    </div>

    <div
      class="photo"
      :style="`background: url(/${recipe.img}) no-repeat center center`"
      :alt="recipe.alt"
    ></div>

    <nav class="internal-nav">
      <h4>Article Sections</h4>
      <ul>
        <li v-for="link of recipe.toc" :key="link.id">
          <NuxtLink :to="`#${link.id}`">{{ link.text }}</NuxtLink>
        </li>
      </ul>
    </nav>

    <article>
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
/* new */
main.single {
  width: calc(100vw - 8vw);
  display: grid;
  grid-template-columns: 1fr 1.5fr 3fr;
  grid-template-rows: 500px 1fr;
  grid-column-gap: 50px;
  grid-row-gap: 60px;
  margin-left: 8vw;
}

.titlearea {
  grid-area: 1 / 1 / 2 / 3;
  padding: 100px 100px 0 0;
}

.photo {
  grid-area: 1 / 3 / 2 / 4;
  background-size: cover;
}

.internal-nav {
  grid-area: 2 / 1 / 3 / 2;
  border-top: 4px solid black;
  padding-top: 10px;
}
.internal-nav h4 {
  padding: 8px;
}
.internal-nav ul {
  padding-left: 0;
}
.internal-nav li {
  border-top: 1px solid grey;
  padding: 8px;
  list-style: none;
  font-size: 14px;
}
.internal-nav a {
  text-decoration: none;
  color: black;
}

article {
  grid-area: 2 / 2 / 3 / 4;
}

/*old */

h1.recipe-title {
  font-size: 45px;
}

.nuxt-content {
  width: 50vw;
  margin-top: -20px;
  margin-bottom: 100px;
}

.nuxt-content h1 {
  font-size: 28px;
  margin: 20px 0;
}

.nuxt-content h2 {
  font-size: 28px;
  margin: 15px 0;
}

.nuxt-content h3 {
  font-size: 22px;
  margin: 10px 0;
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
