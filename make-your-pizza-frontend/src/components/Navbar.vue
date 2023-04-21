<template>
    <nav class="navbar navbar-expand-lg navbar-dark navbar-color">
        <div class="container-fluid">
            <router-link class="navbar-brand" to="/">
                <img src="../assets/logo.png" alt="Logo" class="d-inline-block align-text-top logo">
                <span class="title-page p-1">Monte a Sua Pizza</span>
            </router-link>
            <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNav"
                aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation">
                <span class="navbar-toggler-icon"></span>
            </button>
            <div class="collapse navbar-collapse" id="navbarNav">
                <ul class="navbar-nav">
                    <li class="nav-item">
                        <router-link class="nav-link" aria-current="page" to="/">Início</router-link>
                    </li>
                    <li class="nav-item">
                        <router-link class="nav-link" to="/order">Pedido</router-link>
                    </li>
                </ul>
            </div>
        </div>
    </nav>
</template>

<script>
export default {
    name: "Navbar"
}

</script>
  
<style scoped>
@import '@/assets/css/colors.css';

.navbar-color {
    background-color: var(--var-system-color-delete);
}

.title-page {
    font-weight: 600;
}

.logo {
    width: 30px;
    height: 30px;
}

li{
    font-weight: 700;
}
</style>