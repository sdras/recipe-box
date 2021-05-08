<template>
  <svg
    width="100"
    height="20"
    viewBox="0 -20 200 120"
    xmlns="http://www.w3.org/2000/svg"
  >
    <path
      class="path"
      id="star"
      stroke="#333"
      stroke-width="3"
      d="M50,20a3.51,3.51,0,0,0-3.15,2L39.06,37.74,21.65,40.27a3.51,3.51,0,0,0-1.95,6L32.3,58.55l-3,17.34A3.51,3.51,0,0,0,32.79,80a3.48,3.48,0,0,0,1.63-.4L50,71.41,65.58,79.6a3.48,3.48,0,0,0,1.63.4,3.57,3.57,0,0,0,2.07-.67,3.51,3.51,0,0,0,1.39-3.44l-3-17.34L80.3,46.26a3.51,3.51,0,0,0-2-6L60.94,37.74,53.15,22A3.51,3.51,0,0,0,50,20Z"
    />
    />

    <g fill="white">
      <use v-for="x in 4" :key="x" href="#star" :x="x * 70" />
    </g>

    <g fill="#333">
      <use v-for="num in rating" :key="num" href="#star" :x="num * 70 - 70" />
    </g>
  </svg>
</template>

<script>
export default {
  props: {
    rating: {
      type: Number,
      default: 3
    }
  }
};
</script>

<style scoped>
svg {
  margin-top: -2px;
}
</style>
