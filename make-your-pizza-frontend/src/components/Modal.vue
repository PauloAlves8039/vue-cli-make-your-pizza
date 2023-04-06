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
                        <input type="text" class="form-control" id="name" aria-describedby="emailHelp">
                    </div>
                    <div class="mb-3">
                        <label for="name" class="form-label title-label">Selecione o Sabor</label>
                        <select name="flavor" id="flavor" class="form-select" aria-label="Default select example">
                            <option selected></option>
                            <option value="flavor">One</option>
                            <option value="flavor">Two</option>
                            <option value="flavor">Three</option>
                        </select>
                    </div>
                    <div class="mb-3">
                        <label for="name" class="form-label title-label">Escolha o Recheio</label>
                        <select name="filling" id="filling" class="form-select" aria-label="Default select example">
                            <option selected></option>
                            <option value="filling">One</option>
                            <option value="filling">Two</option>
                            <option value="filling">Three</option>
                        </select>
                    </div>
                    
                    <div>
                        <label class="title-label">Selecione os Opicionais</label>
                    </div>
                    
                    <div class="row mt-1">
                        <div class="col">
                            <div class="mb-2 form-check">
                                <input type="checkbox" class="form-check-input" id="chicken">
                                <label class="form-check-label" for="chicken">Frango</label>
                            </div>
                            <div class="mb-2 form-check">
                                <input type="checkbox" class="form-check-input" id="olive">
                                <label class="form-check-label" for="olive">Azeitona</label>
                            </div>
                            <div class="mb-2 form-check">
                                <input type="checkbox" class="form-check-input" id="artichoke">
                                <label class="form-check-label" for="artichoke">Alcachofra</label>
                            </div>
                        </div>

                        <div class="col">
                            <div class="mb-2 form-check">
                                <input type="checkbox" class="form-check-input" id="broccoli">
                                <label class="form-check-label" for="broccoli">Brócolis</label>
                            </div>
                            <div class="mb-2 form-check">
                                <input type="checkbox" class="form-check-input" id="mushrooms">
                                <label class="form-check-label" for="mushrooms">Cogumelos</label>
                            </div>
                            <div class="mb-2 form-check">
                                <input type="checkbox" class="form-check-input" id="oregano">
                                <label class="form-check-label" for="oregano">Orégano</label>
                            </div>
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
    name: "Modal"
}
</script>
  
<style scoped>
#modal-title-label{
    margin-left: auto;
    color: #15B115;
    font-weight: 700;
}

.title-label {
    font-weight: 600;
}
</style>