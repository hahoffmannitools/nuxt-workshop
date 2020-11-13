<template>
  <div>
    <header>
      <nav class="container mx-auto">
        <ul>
          <li>
            <NuxtLink to="/"> Home </NuxtLink>
          </li>
          <li>
            <nuxt-link to="/about"> About page </nuxt-link>
          </li>
          <li>
            <nuxt-link to="/rivers-fetch">
              Rivers (fetch)
            </nuxt-link>
          </li>
          <li>
            <nuxt-link to="/rivers-async-data">
              Rivers (asyncData)
            </nuxt-link>
          </li>
          <li>
            <nuxt-link to="/beers">
              Beers (content module)
            </nuxt-link>
          </li>
        </ul>
      </nav>
    </header>
    <div class="container mx-auto">
      <Nuxt />
    </div>
  </div>
</template>

<style>
html {
  font-family: "Source Sans Pro", -apple-system, BlinkMacSystemFont, "Segoe UI",
    Roboto, "Helvetica Neue", Arial, sans-serif;
  font-size: 16px;
  word-spacing: 1px;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  box-sizing: border-box;
}

*,
*::before,
*::after {
  box-sizing: border-box;
  margin: 0;
}

.button--green {
  display: inline-block;
  border-radius: 4px;
  border: 1px solid #3b8070;
  color: #3b8070;
  text-decoration: none;
  padding: 10px 30px;
}

.button--green:hover {
  color: #fff;
  background-color: #3b8070;
}

.button--grey {
  display: inline-block;
  border-radius: 4px;
  border: 1px solid #35495e;
  color: #35495e;
  text-decoration: none;
  padding: 10px 30px;
  margin-left: 15px;
}

.button--grey:hover {
  color: #fff;
  background-color: #35495e;
}

nav ul li {
  @apply underline;
  display: inline-block;
  padding: 12px;
}

.btn {
  @apply font-bold py-2 px-4 rounded;
}
.btn-blue {
  @apply bg-blue-500 text-white;
}
.btn-blue:hover {
  @apply bg-blue-700;
}
.btn-outline {
  @apply bg-white text-gray-800 font-semibold border border-gray-400 shadow
}
.btn-outline:hover {
  @apply bg-gray-100
}
h1 {
  margin-bottom: 10px;
}
</style>
