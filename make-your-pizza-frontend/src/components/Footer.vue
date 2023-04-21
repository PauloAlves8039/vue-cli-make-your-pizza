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

.footer-color {
    background-color: var(--var-system-color-delete);
}

.footer {
    border-top: 1px solid;
    color: #FFF;
    text-align: center;
    bottom: 0;
    left: 0;
    height: 35px;
    position: fixed;
    width: 100%;
}
</style>