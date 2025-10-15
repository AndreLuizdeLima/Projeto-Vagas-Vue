<template>
    <div class="container py-4">
        <div class="row">
            <div class="col">
                <h4>Cadastre sua vaga</h4>
            </div>
        </div>

        <div class="row">
            <div class="col">
                <label class="form-label mt-3">Titulo da Vaga</label>
                <input type="text" class="form-control">
                <div class="form-text">Por exemplo: Programador JavaScript e VueJs</div>
            </div>
        </div>

        <div class="row">
            <div class="col">
                <label class="form-label mt-3">Descrição</label>
                <textarea type="text" class="form-control"></textarea>
                <div class="form-text">Informe detalhes da vaga</div>
            </div>
        </div>

         <div class="row">
            <div class="col">
                <label class="form-label mt-3">Salario</label>
                <input type="number" class="form-control">
                <div class="form-text">Informe o salario</div>
            </div>

            <div class="col">
                <label class="form-label mt-3">Modalidade</label>
                <select class="form-select">
                    <option value="1">Home Office</option>
                    <option value="2">Presencial</option>
                </select>
                <div class="form-text">Informe onde as atividades serão realizadas</div>
            </div>

            <div class="col">
                <label class="form-label mt-3">Tipo</label>
                <select class="form-select">
                    <option value="1">CLT</option>
                    <option value="2">PJ</option>
                </select>
                <div class="form-text">Informe o tipo de contratação</div>
            </div>
        </div>

        <div class="row mt-3">
            <div class="col">
                <button type="submit" class="btn btn-primary">Cadastrar</button>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'PublicarVaga'
}
</script>

<style></style>