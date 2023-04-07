<template>
    <div class="modal fade" id="modal-pizza" tabindex="-1" aria-labelledby="exampleModalLabel" aria-hidden="true">
        <div class="modal-dialog">
            <div class="modal-content">
                <div class="modal-header">
                    <h5 class="modal-title" id="modal-title-label">Montagem de Pizza</h5>
                    <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
                </div>
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
                        <div class="col-sm-4 mb-2 form-check form-check-inline" v-for="optional in optionalData" :key="optional.id">
                            <input type="checkbox" class="form-check-input" :value="optional.type">
                            <span>{{ optional.type }}</span>
                        </div>
                    </div>
                </div>
                <div class="modal-footer">
                    <button type="button" class="btn btn-outline-danger" data-bs-dismiss="modal">
                        <i class="bi bi-x-lg"></i>
                    </button>
                    <button type="button" class="btn btn-outline-success">
                        <i class="bi bi-check-lg"></i>
                    </button>
                </div>
            </div>
        </div>
    </div>
</template>
  
<script>
export default {
    name: "Modal",
    data() {
        return {
            flavors: null,
            fillings: null,
            optionalData: null,
            name: null,
            flavor: null,
            filling: null,
            optional: [],
            status: 'Solicitado',
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
        }
    },
    mounted() {
        this.getIngredients();
    }
}
</script>
  
<style scoped>
#modal-title-label {
    margin-left: auto;
    color: #15B115;
    font-weight: 700;
}

.title-label {
    font-weight: 600;
}

.check-optional {
    margin-left: 0;
}
</style>