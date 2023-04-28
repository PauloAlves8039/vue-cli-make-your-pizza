<template>
    <div class="footer footer-color">
        <p class="mt-1">
            Monte a Sua Pizza &copy; {{ new Date().getFullYear() }}
        </p>
    </div>
</template>
  
<script>
export default {
    name: "Footer"
}
</script>
  
<style scoped>
@import '@/assets/css/colors.css';
@import '@/assets/css/footer.css';
</style>