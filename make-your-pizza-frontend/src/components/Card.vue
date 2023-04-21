<template>
    <div class="container-card row">
        <div class="card text-dark mb-3 col-8 card-total">
            <div class="card-body">
                <p class="card-text">
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

.container-card {
    display: flex;
    justify-content: center;
}

.card-total {
    background-color: var(--var-system-color-info);
    max-width: 16rem;
    max-height: 3rem;
}

.card-text {
    color: var(--var-system-color-white);
    font-size: 18px;
    font-weight: 400;
    text-align: center;
    margin-top: -5px;
}

.text-total {
    font-weight: 700;
}
</style>