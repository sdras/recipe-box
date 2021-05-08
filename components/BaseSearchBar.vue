<template>
  <div class="bar">
    <label for="searchbar">Search for your ideal recipe</label>
    <base-search-input />
  </div>
</template>

<script>
export default {};
</script>

<style scoped>
.bar {
  width: 1100px;
  padding: 30px 60px;
  display: table;
  margin: 0 auto;
  z-index: 100;
  position: relative;
  background: white;
  margin-top: -40px;
  box-shadow: 0 10px 20px 5px rgba(0, 0, 0, 0.1);
  display: flex;
}

label {
  margin-right: 20px;
  font-family: "Quarto A", "Quarto B";
  font-size: 21px;
  font-style: normal;
  font-weight: 400;
}
</style>
