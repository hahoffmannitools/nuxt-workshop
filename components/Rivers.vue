<template>
  <p class="p-3" v-if="$fetchState.pending">Fetching rivers...</p>
  <p class="p-3" v-else-if="$fetchState.error">
    An error occurred :( {{ $fetchState.error.message }}
  </p>
  <div v-else>
  <!-- <div> -->
    <h1 class="text-2xl p-3">Rivers (fetch)</h1>
    <ul>
      <li class="p-3" v-for="river of rivers" :key="river.title">
        <div class="rounded shadow-lg p-3 pb-6">
          <img class="mb-3" :src="river.image" />
          <h1 class="text-xl">{{ river.title }}</h1>
          <p class="mb-3">{{ river.description }}</p>
          <p class="mb-3">{{ river.continent }}</p>
          <nuxt-link class="btn btn-outline" :to="`/river/${river.slug}`">Learn more</nuxt-link>
        </div>
      </li>
    </ul>
    <button class="mt-6 mb-6 p-3 btn btn-blue" @click="$fetch">Refresh</button>
  </div>
</template>

<script>
export default {
  name: "Rivers",
  data() {
    return {
      rivers: [],
    };
  },
  // async asyncData() {
  //   const rivers = await $axios.$get("https://api.nuxtjs.dev/rivers");
  //   return { rivers }
  // },
  async fetch() {
    this.rivers = await fetch(
      "https://api.nuxtjs.dev/rivers"
    ).then((res) => {
      if (res.ok) {
        return res.json();
      } else {
        throw new Error('Error!!!!')
      }
    });
  },
};
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
}
</style>