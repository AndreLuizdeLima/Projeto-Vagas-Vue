<template>
    <!-- 
    <slot name="titulo" :dadosTitulo="{ titulo: 'Titulo Lista', nroVagas: 15}">
        <p>titulo da lista de Vagas</p>
    </slot>
    -->
    <slot :vagas="vagas">
        <div class="row mt-5" v-for="(vaga, index) in vagas" :key="index">
            <div class="col">
                <vagas-publicadas v-bind="vaga" />
            </div>
        </div>
    </slot>

    <!--
    <slot name="rodape" :dadosRodape="{titulo: 'roda-pe Lista', paginacao: {nroPaginas: 10, paginaAtual: 1 }}">
        <p>rodape</p>
    </slot>
    -->
</template>

<script>
import VagasPublicadas from "@/components/comuns/VagasPublicadas.vue"

export default {
    name: 'ListaVagas',
    data: () => ({
        vagas: []
    }),
    components: {
        VagasPublicadas
    },
    activated() {
        this.vagas = JSON.parse(localStorage.getItem('vagas'))
    },
    mounted() {
        this.emitter.on('filtrarVagas', vaga => {
            const vagas = JSON.parse(localStorage.getItem('vagas'))
            this.vagas = vagas.filter(reg => reg.titulo.toLowerCase().includes(vaga.titulo.toLowerCase()))
        })
    }
}
</script>

<style></style>