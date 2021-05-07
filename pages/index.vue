<template>
  <main>
    <h1>Hi there</h1>
    <p>Heya gator</p>
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
<style></style>
