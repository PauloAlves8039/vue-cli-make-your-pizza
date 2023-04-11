<template>
    <table class="table table-hover mt-3">
        <thead>
            <tr class="table-dark title-table">
                <th>Códido</th>
                <th>Cliente</th>
                <th>Sabor</th>
                <th>Recheio</th>
                <th>Opcionais</th>
                <th>Atualziar Estado</th>
                <th>Remover</th>
            </tr>
        </thead>
        <tbody class="text-table">
            <tr>
                <td></td>
                <td></td>
                <td></td>
                <td></td>
                <td>
                    <ul class="text-optional">
                        <li></li>
                    </ul>
                </td>
                <td class="text-table select-state">
                    <select class="form-select">
                        <option></option>
                    </select>
                </td>
                <td>
                    <button class="btn btn-outline-danger button-table">
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
    font-size: 17px;
}

.text-optional {
    font-size: 13px;
}

.select-state {
    margin-left: 15px;
    width: 160px;
}

.button-table {
    width: 100px;
}

li {
    list-style: none;
}
</style>