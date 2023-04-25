<template>
    <div class="alert alert-success" role="alert">
        <p class="text-message mb-1 animation-3s">{{ message }}</p>
    </div>
</template>
  
<script>
export default {
    name: "Message",
    props: {
        message: String
    }
}
</script>
  
<style scoped>
@import '@/assets/css/colors.css';
@import '@/assets/css/animation.css';

.text-message {
    text-align: center;
    font-size: 17px;
    font-weight: 500;
}
</style>