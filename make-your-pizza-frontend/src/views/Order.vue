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
h1 {
  text-align: center;
  color: #19A619;
  font-weight: 600;
}
</style>
