<template>
    <div class="alert alert-success" role="alert">
        <p class="text-message mb-1">{{ message }}</p>
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
.text-message {
    text-align: center;
    font-size: 17px;
    font-weight: 500;
}
</style>