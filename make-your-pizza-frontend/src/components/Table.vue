<template>
    <Message :message="message" v-show="message" />
    <table class="table table-hover mt-3">
        <thead>
            <tr class="table-dark title-table">
                <th>Pedido</th>
                <th>Cliente</th>
                <th>Sabor</th>
                <th>Recheio</th>
                <th>Opcionais</th>
                <th>Estado</th>
                <th>Remover</th>
            </tr>
        </thead>
        <tbody class="text-table">
            <tr v-for="pizza in pagedData" :key="pizza.id">
                <td>{{ pizza.id }}</td>
                <td>{{ pizza.name }}</td>
                <td>{{ pizza.flavor }}</td>
                <td>{{ pizza.filling }}</td>
                <td>
                    <ul class="text-optional">
                        <li v-for="(option, index) in pizza.optional" :key="index">
                            {{ option }}
                        </li>
                    </ul>
                </td>
                <td class="text-table select-state">
                    <select class="form-select" @change="updateOrder($event, pizza.id)">
                        <option v-for="state in status" :key="state.id" :value="state.type" :selected="pizza.status == state.type">
                            {{ state.type }}
                        </option>
                    </select>
                </td>
                <td>
                    <button class="btn btn-outline-danger button-table" @click="deleteOrder(pizza.id)">
                        <i class="bi bi-trash3-fill"></i>
                    </button>
                </td>
          </tr>
        </tbody>
    </table>
    <Pagination :inputData="pizzas" v-model:pagedData="pagedData" :elementsPerPage="elementsPerPage" />
</template>
  
<script>
import Message from '@/components/Message.vue';
import Pagination from '@/components/Pagination.vue';

export default {
    name: "Table",
    components: {
        Message,
        Pagination
    },
    data() {
        return {
            pizzas: [],
            pizzas_id: null,
            status: [],
            message: null,
            pagedData: [],
            elementsPerPage: 5,
            url: "http://localhost:3001"
        }
    },
    methods: {
        async getOrders() {
            const request = await fetch(`${this.url}/pizzas`);
            const data = await request.json();

            this.pizzas = data;

            this.getStatus();
        },
        async getStatus() {
            const request = await fetch(`${this.url}/status`);
            const data = await request.json();

            this.status = data;
        },
        async updateOrder(event, id) {
            const option = event.target.value;
            const dataJson = JSON.stringify({ status:option });

            const request = await fetch(`${this.url}/pizzas/${id}`, {
                method: "PATCH",
                headers: { "Content-Type": "application/json" },
                body: dataJson
            });

            const response = await request.json();
            this.alertSuccessMessage(response.id, response.status);

        },
        async deleteOrder(id) {
            const request = await fetch(`${this.url}/pizzas/${id}`, {method: "DELETE"});
            const response = await request.json();

            this.alertDeleteMessage(id);
            this.getOrders();
        },
        alertSuccessMessage(value, state) {
            this.message = `Pedido N° ${value} foi atualizado para ${state}!`;
            setTimeout(() => this.message = "", 4000);
        },
        alertDeleteMessage(value) {
            this.message = `Pedido N° ${value} foi removido!`;
            setTimeout(() => this.message = "", 4000);
        }
    },
    mounted() {
        this.getOrders();
    }
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