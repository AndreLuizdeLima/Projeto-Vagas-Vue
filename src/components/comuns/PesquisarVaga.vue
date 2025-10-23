<template>
    <div class="h100 p-5 bg-light border rounded-3">

        <h2>Pesquisar vagas</h2>
        <div class="row">
            <div class="col">
                <div class="form-group">
                    <label>Titulo da vaga</label>
                    <input type="text" class="form-control" v-model="titulo"
                        placeholder="pesquisa por palavras chaves, por exemplo 'php', 'Senior', 'DBA'">
                    <small class="form-text text-muted">Informe palavras que estão relacionadas com o titulo da vaga que
                        procura.</small>
                </div>
            </div>
        </div>

        <div class="row">
            <div class="col">
                <button class="btn btn-outline-dark mt-2" type="button" @click="pesquisarVaga()">Buscar</button>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'PesquisarVaga',
    data: () => ({
        titulo: ''
    }),
    methods: {
        pesquisarVaga() {
            this.emitter.emit('filtrarVagas', {titulo: this.titulo})
        }
    }
}
</script>

<style></style>