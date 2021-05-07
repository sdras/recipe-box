<template>
  <recipe>
    <nuxt-content :document="recipe" />
  </recipe>
</template>

<script>
export default {
  async asyncData({ $content, params }) {
    const recipe = await $content("recipes", params.slug).fetch();

    return { recipe };
  }
};
</script>
