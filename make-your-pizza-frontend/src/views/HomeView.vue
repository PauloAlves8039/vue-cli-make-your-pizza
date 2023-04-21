<template>
  <div class="home">
    <div class="container">
      <Carousel />
      <Modal />
      <div class="div-modal">
          <button type="button" class="btn modal-button-order mt-2 button-modal" data-bs-toggle="modal" data-bs-target="#modal-pizza">
            <span class="button-text">
              Adicione seu pedido
              <i class="bi bi-plus-circle"></i>
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
@import '@/assets/css/colors.css';

.modal-button-order {
  background-color: var(--var-system-color-white);
  color: var(--var-system-color-success);
  border-color: var(--var-system-color-success);
}

.modal-button-order:hover {
  background-color: var(--var-system-color-success);
  color: var(--var-system-color-white);
  border-color: var(--var-system-color-success);
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
