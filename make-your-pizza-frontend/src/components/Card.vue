<template>
    <div class="container-card row">
        <div class="card text-dark mb-3 col-8 card-total">
            <div class="card-body">
                <p class="card-text animation-3s">
                    Total de Pedidos:
                    <span class="text-total">{{ total }}</span>
                </p>
            </div>
        </div>
    </div>
    
</template>
  
<script>
export default {
    name: "Card",
    props: {
        total: {
            type: Number,
            required: true
        }
    }
}
</script>
  
<style scoped>
@import '@/assets/css/colors.css';
@import '@/assets/css/animation.css';
@import '@/assets/css/card.css';
</style>