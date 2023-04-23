<template>
    <div class="py-2">
        <h2 class="contact-title">Contatos</h2>
    </div>
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

.contact-container {
    display: flex;
    justify-content: center;
}

.contact-title {
    text-align: center;
}

.contact-body {
    width: 50px;
    height: 50px;
    border-radius: 10px;
}

.contact-color-whatsapp {
    background-color: var(--var-system-color-success);
    color: var(--var-system-color-white);
}

.contact-color-telephone {
    background-color: var(--var-system-color-info);
    color: var(--var-system-color-white);
}

.contact-color-instagram {
    background: radial-gradient(circle at 30% 107%, #fdf497 0%, #fdf497 5%, #fd5949 45%, #d6249f 60%, #285AEB 90%);
    color: var(--var-system-color-white);
}

.contact-icon {
    font-size: 32px;
    margin-top: -5px;
    margin-left: 10px;
}
</style>