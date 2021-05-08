<template>
  <div class="author">
    <span>Written by {{ author.name }}</span>
    <img :src="author.image" />
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
  margin-left: 8px;
}

.author {
  display: flex;
  align-items: center;
  justify-content: flex-end;
  font-size: 80%;
}
</style>
