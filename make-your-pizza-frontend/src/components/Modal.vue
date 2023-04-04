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
                        <label for="name" class="form-label title-label">Escolha o Sabor</label>
                        <input type="text" class="form-control" id="name" aria-describedby="emailHelp">
                    </div>
                    <div class="mb-3">
                        <label for="name" class="form-label title-label">Escolha o Recheio</label>
                        <input type="text" class="form-control" id="name" aria-describedby="emailHelp">
                    </div>
                    
                    <div>
                        <label class="title-label">Selecione os Opicionais</label>
                    </div>
                    
                    <div class="row mt-1">
                        <div class="col">
                            <div class="mb-2 form-check">
                                <input type="checkbox" class="form-check-input" id="exampleCheck1">
                                <label class="form-check-label" for="exampleCheck1">Frango</label>
                            </div>
                            <div class="mb-2 form-check">
                                <input type="checkbox" class="form-check-input" id="exampleCheck1">
                                <label class="form-check-label" for="exampleCheck1">Azeitona</label>
                            </div>
                            <div class="mb-2 form-check">
                                <input type="checkbox" class="form-check-input" id="exampleCheck1">
                                <label class="form-check-label" for="exampleCheck1">Alcachofra</label>
                            </div>
                        </div>

                        <div class="col">
                            <div class="mb-2 form-check">
                                <input type="checkbox" class="form-check-input" id="exampleCheck4">
                                <label class="form-check-label" for="exampleCheck1">Brócolis</label>
                            </div>
                            <div class="mb-2 form-check">
                                <input type="checkbox" class="form-check-input" id="exampleCheck5">
                                <label class="form-check-label" for="exampleCheck1">Cogumelos</label>
                            </div>
                            <div class="mb-2 form-check">
                                <input type="checkbox" class="form-check-input" id="exampleCheck6">
                                <label class="form-check-label" for="exampleCheck1">Orégano</label>
                            </div>
                        </div>

                    </div>
                </div>
                <div class="modal-footer">
                    <button type="button" class="btn btn-outline-dark" data-bs-dismiss="modal">Fechar</button>
                    <button type="button" class="btn btn-outline-success">Criar Minha Pizza</button>
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