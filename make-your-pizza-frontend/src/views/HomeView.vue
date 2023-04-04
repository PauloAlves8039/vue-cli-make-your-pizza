<template>
  <div class="home">
    <h2 class="title-home">Make Your Pizza</h2>
    <div class="container">
      <Carousel />
      <Modal />
      <div class="div-modal">
          <button type="button" class="btn btn-outline-primary mt-2 button-modal" data-bs-toggle="modal" data-bs-target="#modal-pizza">
            <span class="button-text">
              Monte a Sua Pizza
            </span>
          </button>
      </div>
    </div>
  </div>
</template>

<script>
import Carousel from '@/components/Carousel.vue';
import Modal from '@/components/Modal.vue';

export default {
  name: 'HomeView',
  components: {
    Carousel,
    Modal
  }
}
</script>

<style scoped>
.title-home {
  text-align: center;
  color: #15B115;
  font-weight: 700;
}

.div-modal {
  text-align: center;
}

.button-modal {
  width: 300px;
}

.button-text {
  font-size: 18px;
}
</style>
