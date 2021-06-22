<template>
  <main>
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
              :aria-label="recipe.title"
              role="img"
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
            <tag-group :tags="recipe.tags"></tag-group>
            <p class="description">{{ recipe.description }}</p>
          </div>
        </div>
      </div>
    </section>
  </main>
</template>

<script>
import TagGroup from "../components/global/TagGroup.vue";
export default {
  components: { TagGroup },
  async asyncData({ $content, params }) {
    const recipes = await $content("recipes")
      .only([
        "title",
        "description",
        "img",
        "slug",
        "time",
        "rating",
        "tags",
        "order"
      ])
      .sortBy("order")
      .fetch();

    return {
      recipes
    };
  }
};
</script>

<style scoped>
.recipe-list-img {
  height: 200px;
  border-radius: 5px;
  background-size: cover !important;
  position: relative;
}

.tag-group {
  margin: 10px 0 20px;
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
