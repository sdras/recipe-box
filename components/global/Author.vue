<template>
  <div class="author">
    <img :src="author.image" />
    <span>{{ author.name }}</span>
  </div>
</template>

<script>
export default {
  props: {
    author: {
      type: Object,
      required: true
    }
  }
};
</script>

<style scoped>
img {
  width: 40px;
  height: 40px;
  border: 1px solid rgb(104, 104, 104);
  padding: 2px;
  border-radius: 1000px;
  margin-right: 5px;
}

.author {
  display: flex;
  align-items: center;
}
</style>
