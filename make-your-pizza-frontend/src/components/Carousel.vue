<template>
    <div id="carousel-pizza" class="carousel slide" data-bs-ride="carousel">

        <div class="carousel-indicators">
            <button type="button" data-bs-target="#carousel-pizza" data-bs-slide-to="0" class="active"></button>
            <button type="button" data-bs-target="#carousel-pizza" data-bs-slide-to="1"></button>
            <button type="button" data-bs-target="#carousel-pizza" data-bs-slide-to="2"></button>
        </div>

        <div class="carousel-inner">
            <div class="carousel-item active" data-bs-interval="4000">
                <img src="../assets/images/pizza1.jpg" alt="Pizza 1" class="d-block carousel-image">
                <div class="carousel-caption d-none d-md-block carousel-text">
                    <h5>Opções de Sabores</h5>
                    <p>Escolha um sabor preferido para a sua pizza.</p>
                </div>
            </div>
            <div class="carousel-item" data-bs-interval="4000">
                <img src="../assets/images/pizza2.jpg" alt="Pizza 2" class="d-block carousel-image">
                <div class="carousel-caption d-none d-md-block carousel-text">
                    <h5>Montagem de pizza</h5>
                    <p>Selecione a forma como deseja montar sua pizza.</p>
                </div>
            </div>
            <div class="carousel-item" data-bs-interval="4000">
                <img src="../assets/images/pizza3.jpg" alt="Pizza 3" class="d-block carousel-image">
                <div class="carousel-caption d-none d-md-block carousel-text">
                    <h5>Recheios extras</h5>
                    <p>Adicione ingredientes extras a sua pizza montada.</p>
                </div>
            </div>
        </div>

        <button class="carousel-control-prev" type="button" data-bs-target="#demo" data-bs-slide="prev">
            <span class="carousel-control-prev-icon"></span>
        </button>
        <button class="carousel-control-next" type="button" data-bs-target="#demo" data-bs-slide="next">
            <span class="carousel-control-next-icon"></span>
        </button>
    </div>
</template>
  
<script>
export default {
    name: "Carousel"
}
</script>
  
<style scoped>
@import '@/assets/css/colors.css';

.carousel-image {
    width: 100%;
    height: 26rem;
}

.carousel-text {
    text-shadow: 0.2em 0.2em 0.2em var(--var-system-color-black);
    font-weight: 600;
}
</style>