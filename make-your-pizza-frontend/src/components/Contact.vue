<template>
    <div class="container contact-container px-2 py-1" id="featured-3">
        <div class="row g-3 py-1 row-cols-1 row-cols-lg-3">
            <div class="feature col">
            <div class="contact-body contact-color-whatsapp">
                <i class="bi bi-whatsapp contact-icon"></i>
            </div>
            </div>
            <div class="feature col">
                <div class="contact-body contact-color-telephone">
                    <i class="bi bi-telephone contact-icon"></i>
                </div>
            </div>
            <div class="feature col">
                <div class="contact-body contact-color-instagram">
                    <i class="bi bi-instagram contact-icon"></i>
                </div>
            </div>
        </div>
    </div>
</template>
<script>
export default {
    name: 'Contact'
}
</script>
<style scoped>
@import '@/assets/css/colors.css';
@import '@/assets/css/contact.css';
</style>