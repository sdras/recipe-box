<template>
  <div class="prevnext">
    <NuxtLink
      v-if="prev"
      :to="{ name: 'recipes-slug', params: { slug: prev.slug } }"
      class="text-primary font-bold hover:underline"
    >
      <IconArrow style="transform:scaleX(-1)" /> Previous
    </NuxtLink>
    <span v-else>&nbsp;</span>
    <NuxtLink
      v-if="next"
      :to="{ name: 'recipes-slug', params: { slug: next.slug } }"
      class="font-bold hover:underline"
    >
      Next <IconArrow />
    </NuxtLink>
    <span v-else>&nbsp;</span>
  </div>
</template>

<script>
export default {
  props: {
    prev: {
      type: Object,
      default: () => null
    },
    next: {
      type: Object,
      default: () => null
    }
  }
};
</script>

<style scoped>
.prevnext {
  margin: 20px 0 70px;
  display: flex;
  justify-content: space-between;
  width: 400px;
}

@media screen and (max-width: 700px) {
  .prevnext {
    width: calc(100vw - 70px);
  }
}
</style>
