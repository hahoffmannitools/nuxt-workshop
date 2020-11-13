<template>
  <div class="p-3">
    <h1 class="text-2xl">Rivers (asyncData)</h1>
    <pre>{{ $data }}</pre>
  </div>
</template>
<script>
export default {  
  async asyncData ({ $axios }) {    
    const rivers = await $axios.$get('https://api.nuxtjs.dev/rivers')    
    return { rivers }  }
  }
</script>