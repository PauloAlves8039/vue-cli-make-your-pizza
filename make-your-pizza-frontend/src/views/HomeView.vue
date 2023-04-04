<template>
  <div class="home">
    <h2 class="title-home">Make Your Pizza</h2>
    <div class="container">
      <Carousel />
    </div>
  </div>
</template>

<script>
import Carousel from '@/components/Carousel.vue';

export default {
  name: 'HomeView',
  components: {
    Carousel
  }
}
</script>

<style scoped>
.title-home {
  text-align: center;
  color: #15B115;
  font-weight: 700;
}
</style>
