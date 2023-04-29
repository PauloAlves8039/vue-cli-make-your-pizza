<template>
    <Message :message="message" v-show="message" />
    <Card :total="pizzas.length" />
    <Pagination :receivedList="pizzas" v-model:paginatedList="paginatedList" :elementsPerPage="elementsPerPage" />
    <table class="table table-hover mt-3">
        <thead>
            <tr class="title-table">
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
            <tr v-for="pizza in paginatedList" :key="pizza.id">
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
                        <option v-for="state in status" :key="state.id" :value="state.type" :selected="pizza.status === state.type">
                            {{ state.type }}
                        </option>
                    </select>
                </td>
                <td>
                    <button class="btn btn-outline-danger button-table" @click="deleteOrder(pizza.id)" title="Remover">
                        <i class="bi bi-trash3-fill"></i>
                    </button>
                </td>
          </tr>
        </tbody>
    </table>
</template>
  
<script>
import Message from '@/components/Message.vue';
import Pagination from '@/components/Pagination.vue';
import Card from '@/components/Card.vue';

export default {
    name: "Table",
    components: {
        Message,
        Pagination,
        Card
    },
    data() {
        return {
            pizzas: [],
            paginatedList: [],
            status: [],
            pizzas_id: null,
            message: null,            
            elementsPerPage: 5,
            url: "http://localhost:3001"
        }
    },
    methods: {
        async getOrders() {
            const request = await `${this.url}/pizzas`;

            fetch(request)
            .then(reponse => {
                return reponse.json();
            })
            .then(data => {
                this.pizzas = data;
                this.getStatus();
            })
            .catch(error => console.error(error));
        },
        async getStatus() {
            const request = await `${this.url}/status`;

            fetch(request)
            .then(reponse => {
                return reponse.json();
            })
            .then(data => {
                this.status = data;
            })
            .catch(error => console.error(error));
        },
        async updateOrder(event, id) {
            const request = await `${this.url}/pizzas/${id}`;
            const option = event.target.value;
            const dataJson = JSON.stringify({ status:option });

            fetch(request, {
                method: "PATCH",
                headers: { "Content-Type": "application/json" },
                body: dataJson
            })
            .then(response => response.json())
            .then(data => {
                this.alertSuccessMessage(data.id, data.status);
            })
            .catch(error => console.error(error));
        },
        async deleteOrder(id) {
            const request = await `${this.url}/pizzas/${id}`;

            fetch(request, {
                method: "DELETE",
                headers: { "Content-Type": "application/json" }
            }
            )
                .then(response => response.json())
                .catch(error => console.error(error));

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
@import '@/assets/css/colors.css';
@import '@/assets/css/animation.css';
@import '@/assets/css/table.css';
</style>