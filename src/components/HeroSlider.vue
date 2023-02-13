<template>
    <section class="home-hero">
        <Carousel ref="carousel" v-model="currentSlide" snapAlign="start">
        <Slide v-for="slide in 10" :key="slide">
            <div class="carousel__item">{{ slide - 1 }}</div>
        </Slide>
    
        <template #addons>
            <Navigation />
        </template>
        </Carousel>
    
        <div>
        <button @click="prev">Prev</button>
        <input type="number" min="0" max="9" v-model="currentSlide" />
        <button @click="next">Next</button>
        </div>
    </section>
  </template>
  
  <script>
  // If you are using PurgeCSS, make sure to whitelist the carousel CSS classes
  import 'vue3-carousel/dist/carousel.css'
  import { Carousel, Slide, Pagination, Navigation } from 'vue3-carousel'
  
  export default {
    name: 'App',
    components: {
      Carousel,
      Slide,
      Pagination,
      Navigation,
    },
    data: () => ({
    currentSlide: 0,
    }),
    methods: {
    next() {
      this.$refs.carousel.next()
    },
    prev() {
      this.$refs.carousel.prev()
    },
  },
  }
  </script>

<style lang="scss" scoped>
    .home-hero{
        height: 100vh;
        background-color: #2bb9ce;
    }
</style>
  