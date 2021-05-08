<template>
  <ul class="site-links">
    <li>
      <nuxt-link to="/">Authors</nuxt-link>
    </li>
    <li>
      <nuxt-link to="/">Contact</nuxt-link>
    </li>
  </ul>
</template>

<script>
export default {};
</script>

<style scoped>
a,
a:visited,
a:active {
  text-decoration: none;
  color: white;
}

ul.site-links {
  float: right;
}

.site-links li {
  display: inline-block;
  padding-right: 15px;
}
</style>
