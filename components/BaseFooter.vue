<template>
  <footer>
    <BaseNav :navBreak="true" />
  </footer>
</template>

<script></script>

<style scoped>
footer {
  width: 100%;
  background: black;
  padding: 30px 0;
  color: white;
  height: 250px;
  padding-bottom: 100px;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}

nav {
  line-height: 2;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

nav .logo {
  margin-left: -15px;
}
</style>
