<template>
  <footer>
    <BaseSearchBar :modifiedMargin="false" :bkColor="'black'" />
    <BaseSiteLinks />
  </footer>
</template>

<script>
export default {};
</script>

<style scoped>
footer {
  width: 100%;
  background: black;
  padding: 30px 0;
  color: white;
  height: 300px;
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>
