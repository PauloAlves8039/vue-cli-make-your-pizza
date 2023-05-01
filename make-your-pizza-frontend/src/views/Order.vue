<template>
  <div>
    <div class="container">
      <h1>Gerenciar pedidos</h1>
      <Table />
    </div>
  </div>
</template>

<script>
import Table from "@/components/Table.vue";
export default {
  name: "Order",
  components: {
    Table
  }
}
</script>

<style scoped>
@import '@/assets/css/colors.css';

h1 {
  text-align: center;
  color: var(--var-system-color-success);
  font-weight: 600;
}
</style>
