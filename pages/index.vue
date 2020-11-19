<template>
  <div class="p-3">
    <h1 class="text-2xl">Home</h1>
    
    <!-- <img class="image" src="~/assets/my-image.jpg" /> -->
    <!-- assets -->
    <!--
      <img src="/my-image.jpg" />  // static  
      background: url('~assets/${image}.jpg')" // background 
      <img src="require('~/assets/${image}.jpg')"  /> // dynamic
      <LazyComponent /> 
      <button @click="toggleAlert">Click Me</button>
    -->

    <BaseButton @buttonClick="toggleAlert"/>
    
    <LazyBaseAlert @closeAlert="show = !show" v-if="show"/>
    
  </div>
</template>

<script>
export default {
  data() {
    return {
      show: false
    }
  },
  methods: {
    toggleAlert() {
      console.log('click')
      this.show = !this.show
    }
  }
};
</script>
