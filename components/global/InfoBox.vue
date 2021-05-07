<template>
  <div class="infobox">
    <p><slot name="info-box">default</slot></p>
  </div>
</template>

<style scoped>
.infobox {
  background: aliceblue;
  padding: 20px;
  margin: 20px;
  width: 300px;
}
</style>
