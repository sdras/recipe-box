<template>
  <main>
    <base-hero />
    <base-search-bar />

    <section>
      <div class="recipe-piece">
        <div v-for="recipe of recipes" :key="recipe.slug">
          <NuxtLink
            :to="{ name: 'recipes-slug', params: { slug: recipe.slug } }"
          >
            <div
              class="recipe-list-img"
              :style="`background: url(/${recipe.img}) no-repeat center center`"
            ></div>
          </NuxtLink>

          <div class="recipe-content">
            <p class="details">
              <IconTime />{{ recipe.time }} minutes
              <span class="rating"><StarRating :rating="recipe.rating"/></span>
            </p>

            <NuxtLink
              :to="{ name: 'recipes-slug', params: { slug: recipe.slug } }"
              ><h3>{{ recipe.title }}</h3></NuxtLink
            >

            <author :author="recipe.author" />
            <p class="description">{{ recipe.description }}</p>
          </div>
        </div>
      </div>
    </section>
  </main>
</template>

<script>
export default {
  async asyncData({ $content, params }) {
    const recipes = await $content("recipes")
      .only([
        "title",
        "description",
        "img",
        "slug",
        "author",
        "time",
        "rating",
        "tags",
        "meal"
      ])
      .sortBy("createdAt", "desc")
      .fetch();

    return {
      recipes
    };
  }
};
</script>

<style>
.recipe-list-img {
  height: 250px;
  border-radius: 5px;
  background-size: cover !important;
  position: relative;
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
  text-decoration: none;
}

.recipe-piece a {
  color: black;
  text-decoration: none;
}

h3 {
  padding: 5px 0 0;
}

.recipe-content {
  padding: 10px 3px 10px;
}

.description {
  margin: 10px 0;
}

.details {
  font-size: 80%;
}

.rating {
  float: right;
}
</style>
