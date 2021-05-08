<template>
  <div class="tag-group">
    <div v-for="tag in tags" :key="tag" class="tag">{{ tag }}</div>
  </div>
</template>

<script>
export default {
  props: {
    tags: {
      type: Array,
      default: ["Shrimp", "Sauce"]
    }
  }
};
</script>

<style scoped>
.tag {
  font-size: 12px;
  border: 1px solid grey;
  padding: 2px 6px;
  display: inline-block;
  margin-right: 6px;
  text-transform: uppercase;
  border-radius: 2px;
}
</style>
