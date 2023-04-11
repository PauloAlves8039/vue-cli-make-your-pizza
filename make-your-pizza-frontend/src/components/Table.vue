<template>
    <table class="table mt-3">
        <thead>
            <tr class="table-dark title-table">
                <th>Códido do Pedido</th>
                <th>Cliente</th>
                <th>Sabor</th>
                <th>Recheio(s)</th>
                <th>Opcionais</th>
                <th>Ações</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td class="text-table"></td>
                <td class="text-table"></td>
                <td class="text-table"></td>
                <td class="text-table"></td>
                <td>
                    <ul class="text-optional">
                        <li></li>
                    </ul>
                </td>
                <td class="text-table row">
                    <select class="form-select form-select-sm col">
                        <option></option>
                    </select>
                    <button class="btn btn-danger col ms-1">
                        <i class="bi bi-trash3-fill"></i>
                    </button>
                </td>
          </tr>
        </tbody>
    </table>
</template>
  
<script>
export default {
    name: "Table"
}
</script>
  
<style scoped>
.title-table, .text-table {
    text-align: center;
}

.text-table {
    font-size: 14px;
}

.text-optional {
    font-size: 12px;
}
</style>