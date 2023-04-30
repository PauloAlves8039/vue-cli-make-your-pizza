<template>
    <div class="container py-3">
        <div class="card">
            <h1 class="title-about">Monte sua Pizza</h1>
            <div class="card-body">
                <h2>Objetivo</h2>
                <p>
                    Esse projeto foi desenvolvido para fins didáticos com intúito de praticar o desenvolvimento com Vue 3 consumindo uma API.
                </p>
                <p>
                    Como funcionalidades essa aplicação permite ao usuário realizar um cadastro para criar pedidos de pizzas,
                    nessa execução podem ser adionados complementos para personalizar o sabor da cada pizza, 
                    com a montagem dos pedidos das pizzas o usuário pode manipular o estado do pedido.
                </p>
                <hr>
                <h3>Recursos Utilizados</h3>
                <ul>
                    <li>
                        <a href="https://cli.vuejs.org/" target="_blank" alt="Vue.js 3">Vue CLI</a> 
                    </li>
                    <li>
                        <a href="https://vuejs.org/" target="_blank" alt="Vue.js 3">Vue.js 3</a> 
                    </li>
                    <li>
                        <a href="https://router.vuejs.org/" target="_blank" alt="Vue Router">Vue Router</a>  
                    </li>
                    <li>
                        <a href="https://getbootstrap.com/docs/5.0/getting-started/introduction/" target="_blank" alt="Bootstrap 5">Bootstrap 5</a>
                    </li>
                    <li>
                        <a href="https://icons.getbootstrap.com/" target="_blank" alt="Bootstrap 5">Bootstrap Icons</a>
                    </li>
                    <li>
                        <a href="https://animate.style/" target="_blank" alt="Animate CSS">Animate CSS</a> 
                    </li>
                    <li>
                        <a href="https://www.npmjs.com/package/json-server" target="_blank" alt="Animate CSS">JSON Server</a> 
                    </li>
                </ul>
                <hr>
                <h3>Contatos</h3>
                <Contact />
            </div>
        </div>
    </div>
</template>

<script>
import Contact from '@/components/Contact.vue';

export default {
    name: "AboutView",
    components: {
    Contact
  }
}
</script>

<style scoped>
@import '@/assets/css/colors.css';

.title-about {
    text-align: center;
    color: var(--var-system-color-success);
}

.text-about {
    justify-content: justify;
}
</style>