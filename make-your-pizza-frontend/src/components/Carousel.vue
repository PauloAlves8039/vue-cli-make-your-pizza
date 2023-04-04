<template>
    <div id="carousel-pizza" class="carousel slide" data-bs-ride="carousel">

        <div class="carousel-indicators">
            <button type="button" data-bs-target="#carousel-pizza" data-bs-slide-to="0" class="active"></button>
            <button type="button" data-bs-target="#carousel-pizza" data-bs-slide-to="1"></button>
            <button type="button" data-bs-target="#carousel-pizza" data-bs-slide-to="2"></button>
        </div>

        <div class="carousel-inner">
            <div class="carousel-item active">
                <img src="../assets/images/pizza1.jpg" alt="Pizza 1" class="d-block image-carousel">
            </div>
            <div class="carousel-item">
                <img src="../assets/images/pizza2.jpg" alt="Pizza 2" class="d-block image-carousel">
            </div>
            <div class="carousel-item">
                <img src="../assets/images/pizza3.jpg" alt="Pizza 3" class="d-block image-carousel">
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
.image-carousel {
    width: 100%;
    height: 30rem;
}
</style>