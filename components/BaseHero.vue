<template>
  <div
    class="masthead"
    role="img"
    :aria-label="alt"
    :style="`background: url(${heroImg(img)}) no-repeat center center`"
  >
    <h1>
      {{ title }}
    </h1>
    <p v-if="subtitle" class="subtitle">{{ subtitle }}</p>
  </div>
</template>

<script>
export default {
  props: {
    img: {
      type: String,
      default: "brooke-lark1.jpeg"
    },
    alt: {
      type: String,
      default: "light blue background, photo of ingredients"
    },
    title: {
      type: String,
      default: "The Healthy Dev"
    },
    subtitle: {
      type: String,
      default: "Quick, delicious, healthy meals to keep your brain active."
    }
  },
  methods: {
    heroImg(src) {
      let heroSizes = this.$img.getSizes(src, {
        sizes: "xs:100vw sm:100vw md:100vw lg:100vw",
        modifiers: {
          quality: 70,
          height: "50vh"
        }
      });
      return heroSizes.src;
    }
  }
};
</script>

<style scoped>
.masthead {
  display: flex;
  flex-direction: column;
  justify-content: center;
  text-align: right;
  padding-right: 10vmin;
  width: 100%;
  height: 50vh;
  overflow: hidden;
  background-size: cover !important;
  box-shadow: 0 20px 25px 20px #e6eff1;
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

@media only screen and (max-width: 900px) {
  .masthead {
    align-items: flex-end;
  }

  .subtitle {
    text-align: right;
    max-width: 500px;
  }
}

@media only screen and (max-width: 700px) {
  .subtitle {
    max-width: 200px;
  }
}
</style>
