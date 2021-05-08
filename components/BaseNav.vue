<template>
  <nav>
    <svg
      xmlns="http://www.w3.org/2000/svg"
      viewBox="0 0 10 10"
      width="1"
      height="1"
      role="presentation"
      class="hidden"
    >
      <defs>
        <linearGradient id="grad1" x1="0%" y1="0%" x2="0%" y2="100%">
          <stop
            offset="0%"
            style="stop-color:rgb(200, 200, 200);stop-opacity:1"
          ></stop>
          <stop
            offset="100%"
            style="stop-color:rgb(80, 80, 80);stop-opacity:1"
          ></stop>
        </linearGradient>
      </defs>
    </svg>

    <nuxt-link to="/" exact>
      <span class="logo"
        ><svg
          height="25"
          width="25"
          xmlns="http://www.w3.org/2000/svg"
          viewBox="0 0 16 16"
        >
          <path
            fill="url(#grad1)"
            d="M.04 8c.205 2.856 2.12 5.376 4.96 6.453V15.5a.5.5 0 00.5.5h5a.5.5 0 00.5-.5v-1.047c2.84-1.077 4.754-3.597 4.96-6.453H.04zM8.953 7a.484.484 0 01.112-.114c.013-.009 1.285-.883 2.084-2.598a.5.5 0 11.906.423A8.093 8.093 0 0110.454 7H13.3a5.527 5.527 0 001.159-1.313c1.047-2.024.257-5.178.223-5.311a.5.5 0 00-.847-.219c-.009.008-.827.836-3.558 1.883-.964.369-1.665 1.069-1.975 1.97-.222.648-.324 1.666.313 2.99h.338zM2.412 6.391c.156.237.323.432.494.609h1.999c-.339-.373-.696-.841-.874-1.328a.5.5 0 01.939-.344c.24.657 1.06 1.417 1.356 1.654.006.005.009.013.015.018h.413c.337-.835.268-1.491.12-1.921-.226-.66-.737-1.171-1.438-1.44-1.812-.694-2.362-1.24-2.362-1.24a.499.499 0 00-.852.215c-.024.093-.576 2.299.164 3.732l.026.045z"
          /></svg
      ></span>
    </nuxt-link>
    <base-sitelinks />
  </nav>
</template>

<style scoped>
nav {
  background: black;
  color: white;
  padding: 12px 8vmin;
  position: relative;
  z-index: 1000;
}
a,
a:visited,
a:active {
  text-decoration: none;
  color: white;
}
.logo {
  display: inline;
}
ul.site-links {
  float: right;
}

@media screen and (max-width: 500px) {
  nav {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    margin-left: -10px;
    box-shadow: 0 2px 10px 0 black;
    border: 1px solid #222;
  }
  nav a {
    margin: 0 20px;
  }
  nav svg {
    margin-left: -30px;
  }
}
</style>
