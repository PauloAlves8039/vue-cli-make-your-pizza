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
.container-card {
    display: flex;
    justify-content: center;
}

.card-total {
    background-color: #15B115;
    max-width: 16rem;
    max-height: 3rem;
}

.card-text {
    color: #FFF;
    font-size: 18px;
    font-weight: 400;
    text-align: center;
    margin-top: -5px;
}

.text-total {
    font-weight: 800;
}
</style>