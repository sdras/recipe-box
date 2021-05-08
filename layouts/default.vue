<template>
  <div>
    <BaseNav />
    <Nuxt />
  </div>
</template>

<style>
html {
  font-family: "Whitney A", "Whitney B", -apple-system, BlinkMacSystemFont,
    "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif;
  font-size: 18px;
  line-height: 1.4;
  word-spacing: 1px;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  box-sizing: border-box;
  font-style: normal;
  font-weight: 300;
}

*,
*::before,
*::after {
  box-sizing: border-box;
  margin: 0;
}

.italic,
.next {
  font-family: "Whitney A", "Whitney B";
  font-style: italic;
  font-weight: 500;
}

h1,
h2,
h3,
h4 {
  font-family: "Quarto A", "Quarto B";
  font-style: normal;
  font-weight: 400;
}

button {
  background: #098191;
  transition: background ease 0.25s;
  border-radius: 5px;
  display: inline-block;
  border: none;
  padding: 0.75rem 1.5rem;
  margin: 0;
  text-decoration: none;
  color: #ffffff;
  font-size: 1.2rem;
  cursor: pointer;
  text-align: center;
  -webkit-appearance: none;
  -moz-appearance: none;
}
button:hover {
  background: #63b6b8;
}
button:focus {
  outline: 1px solid #fff;
  outline-offset: -4px;
}
</style>
