<template>
  <div class="masthead" role="img" aria-label="Image Description">
    <h1>
      The Healthy Dev
    </h1>
    <p>Quick, delicious, healthy meals to keep your brain active.</p>
  </div>
</template>

<style scoped>
.masthead {
  display: flex;
  flex-direction: column;
  justify-content: center;
  text-align: right;
  padding-right: 10vmin;
  width: 100%;
  height: 60vh; /* if you don't want it to take up the full screen, reduce this number */
  overflow: hidden;
  background-size: cover !important;
  background: url(~/assets/brooke-lark1.jpeg) no-repeat center center scroll;
}

h1 {
  font-size: 8vmin;
  letter-spacing: 0.03em;
  line-height: 1;
  margin-bottom: 20px;
}

p {
  font-size: 20px;
}
</style>
