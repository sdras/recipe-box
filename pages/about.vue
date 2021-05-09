<template>
  <div>
    <base-hero
      :img="'table.jpg'"
      :alt="'table against white'"
      :title="'About'"
      :subtitle="'All about the Healthy Dev'"
    ></base-hero>
    <section>
      <div>
        <h2>What is it?</h2>
        <p>
          I kicked off this blog for myself, really, to hold some of the things
          I was cooking and make sure I didn't forget what I did. Anyone is
          welcome to use these recipes though.
        </p>
        <p>
          You may notice that I bring up fresh ingredients a lot- you'll find
          that the difference between a good and a poor outcome with these in
          particular because they rely so heavily on vegetables, herbs, and
          spices.
        </p>
      </div>
      <div>
        <h2>Credits</h2>
        <ul>
          <li>
            Homepage and about heroes by
            <a
              href="https://unsplash.com/@brookelark?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText"
              >Brooke Lark</a
            >
            on
            <a
              href="https://unsplash.com/@brookelark?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText"
              >Unsplash</a
            >
          </li>
          <li>
            Frittata photo by
            <a
              href="https://unsplash.com/@anshu18?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText"
              >Anshu A</a
            >
            on
            <a
              href="https://unsplash.com/s/photos/frittata?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText"
              >Unsplash</a
            >
          </li>
          <li>
            Crabcake photo by
            <a href="https://www.flickr.com/photos/dinesarasota/"
              >Larry Hoffman</a
            >.
          </li>
          <li>
            Mushroom photo by
            <a
              href="https://unsplash.com/@sebas_m04?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText"
              >Sébastien Marchand</a
            >
            on
            <a
              href="https://unsplash.com/s/photos/mushrooms?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText"
              >Unsplash</a
            >
          </li>
          <li>
            Chimichurri photo by
            <a href="https://www.flickr.com/photos/polkaroo/"
              >Isabelle Boucher</a
            >
          </li>
        </ul>
      </div>
    </section>
  </div>
</template>

<script>
export default {};
</script>

<style scoped>
a,
a:visited {
  font-family: "Whitney A", "Whitney B";
  font-style: italic;
  font-weight: 500;
}

section {
  flex-direction: column;
}

section div {
  margin: 30px auto 60px;
}
</style>
