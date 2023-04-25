<template>
  <Navbar :logo="logo_src" :alt="app_name" />
  <router-view />
  <Spinner />
  <Footer />
</template>

<script>
import Navbar from './components/Navbar.vue';
import Footer from './components/Footer.vue';
import Spinner from './components/Spinner.vue';

export default {
  name: 'App',
  components: {
    Navbar,
    Footer,
    Spinner
  }
}
</script>

<style>

</style>
