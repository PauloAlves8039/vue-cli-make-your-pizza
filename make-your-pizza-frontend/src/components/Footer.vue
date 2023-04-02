<template>
    <div class="footer bg-danger">
        <p class="mt-3">Make Your Pizza &copy; {{ new Date().getFullYear() }}</p>
    </div>
</template>
  
<script>
export default {
    name: "Footer"
}
</script>
  
<style scoped>
.footer {
    height: 50px;
    color: #FFF;
    display: flex;
    align-items: center;
    justify-content: center;
    width: 100%;
}
</style>