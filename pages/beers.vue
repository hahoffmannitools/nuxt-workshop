<template>
  <div>
    <h1 class="text-2xl p-3">Beers</h1>
    <ul>
      <li class="p-3" v-for="beer of beers" :key="beer.title">
        <div class="rounded shadow-lg p-3 pb-6">
          <img class="mb-3" :src="beer.image_url" />
          <h1 class="text-xl">{{ beer.name }}</h1>
          <p class="pb-3">{{ beer.type }}</p>
          <nuxt-link class="btn btn-outline" :to="`/beer/${beer.slug}`">Learn more</nuxt-link>
        </div>
      </li>
    </ul>
  </div>
</template>
<script>
export default {  
  async asyncData ({ $axios }) {    
    const beers = await $axios.$get('https://api.nuxtjs.dev/beers')
    return { beers }  }
  }
</script>

<style scoped>
h1 {
  margin-bottom: 10px;
}
ul {
  display: flex;
  flex-wrap: wrap;
}
li {
  flex: 0 0 33%;
  @apply mb-8
}
</style>