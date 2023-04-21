<template>
<div class="modal fade" id="modal-pizza" tabindex="-1" aria-labelledby="exampleModalLabel" aria-hidden="true">
    <div class="modal-dialog">
        <form @submit="createPizza">
            <div class="modal-content">
                <div class="modal-header">
                    <h5 class="modal-title" id="modal-title-label">Montagem de Pizza</h5>
                    <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
                </div>
                <Message :message="message" v-show="message" />
                <div class="modal-body">
                    <div class="mb-1">
                        <label for="name" class="form-label title-label">Nome do Cliente</label>
                        <input type="text" class="form-control" id="name" name="name" v-model="name">
                    </div>
                    <div class="mb-3">
                        <label for="name" class="form-label title-label">Escolha o Sabor</label>
                        <select name="flavor" id="flavor" class="form-select" v-model="flavor">
                            <option v-for="flavor in flavors" :key="flavor.id" :value="flavor.type">
                                {{ flavor.type }}
                            </option>
                        </select>
                    </div>
                    <div class="mb-3">
                        <label for="name" class="form-label title-label">Escolha o Recheio</label>
                        <select name="filling" id="filling" class="form-select" v-model="filling">
                            <option v-for="filling in fillings" :key="filling.id" :value="filling.type">{{ filling.type }}</option>
                        </select>
                    </div>
                
                    <div>
                        <label class="title-label">Selecione os Opcionais</label>
                    </div>
                
                    <div class="row mt-1 check-optional">
                        <div class="col-sm-4 mb-2 form-check form-check-inline" v-for="option in optionalData" :key="option.id">
                            <input type="checkbox" class="form-check-input" name="optional" v-model="optional" :value="option.type">
                            <span>{{ option.type }}</span>
                        </div>
                    </div>
                </div>
                <div class="modal-footer">
                    <button type="button" class="btn modal-button-leave modal-button" title="Fechar" data-bs-dismiss="modal">
                        <i class="bi bi-x-circle-fill modal-icon-button"></i>
                    </button>
                    <button type="button" class="btn modal-button-clean modal-button" title="Cancelar" @click="clearFields()">
                        <i class="bi bi-eraser-fill modal-icon-button"></i>
                    </button>
                    <button type="submit" class="btn modal-button-save modal-button" title="Salvar">
                        <i class="bi bi-check-circle-fill modal-icon-button"></i>
                    </button>
                </div>
            </div>
        </form>
    </div>
</div>
</template>
  
<script>
import Message from '@/components/Message.vue';

export default {
    name: "Modal",
    components: {
        Message
    },
    data() {
        return {
            flavors: null,
            fillings: null,
            optionalData: null,
            name: null,
            flavor: null,
            filling: null,
            optional: [],
            message: null
        }
    },
    methods: {
        async getIngredients() {
            const urlIngredients = "http://localhost:3001/ingredients";
            const request = await fetch(urlIngredients);
            const data = await request.json();

            this.flavors = data.flavors;
            this.fillings = data.fillings;
            this.optionalData = data.optional;
        },
        async createPizza(event) {
            const urlPizza = "http://localhost:3001/pizzas";
            event.preventDefault();
            
            const data = {
                name: this.name,
                flavor: this.flavor,
                filling: this.filling,
                optional: Array.from(this.optional),
                status: 'Solicitado',
            }

            const dataJson = JSON.stringify(data);

            const request = await fetch(urlPizza, {
                method: "POST",
                headers: {"Content-Type": "application/json"},
                body: dataJson
            });

            const response = await request.json();

            this.alertSuccessMessage(response.id);
            this.clearFields();
        },
        alertSuccessMessage(value) {
            this.message = `Pedido N° ${value} realizado com sucesso!`;
            setTimeout(() => this.message = "", 4000);
        },
        clearFields() {
            this.name = "",
            this.flavor = "",
            this.filling = "",
            this.optional = []
        }
    },
    mounted() {
        this.getIngredients();
    }
}
</script>
  
<style scoped>
@import '@/assets/css/colors.css';

#modal-title-label {
    margin-left: auto;
    color: var(--var-system-color-success);
    font-weight: 700;
}

.title-label {
    font-weight: 600;
}

.check-optional {
    margin-left: 0;
}

.modal-button {
    width: 100px;
    height: 40px;
}

.modal-button-save {
    background-color: var(--var-system-color-white);
    color: var(--var-system-color-success);
    border-color: var(--var-system-color-success);
}

.modal-button-save:hover {
    background-color: var(--var-system-color-success);
    color: var(--var-system-color-white);
    border-color: var(--var-system-color-success);
}

.modal-button-clean {
    background-color: var(--var-system-color-white);
    color: var(--var-system-color-delete);
    border-color: var(--var-system-color-delete);
}

.modal-button-clean:hover {
    background-color: var(--var-system-color-delete);
    color: var(--var-system-color-white);
    border-color: var(--var-system-color-delete);
}

.modal-button-leave {
    background-color: var(--var-system-color-white);
    color: var(--var-system-color-closed);
    border-color: var(--var-system-color-closed);
}

.modal-button-leave:hover {
    background-color: var(--var-system-color-closed);
    color: var(--var-system-color-white);
    border-color: var(--var-system-color-closed);
}

.modal-icon-button {
    font-size: 18px;
}

.modal-footer {
    justify-content: center;
}
</style>