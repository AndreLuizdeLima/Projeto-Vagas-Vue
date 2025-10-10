<template>
    <div class="container py-4">
        <div class="row">
            <div class="col">
                <pesquisar-vaga />
            </div>
        </div>
        <div class="row mt-5 text-center">
            <div class="col-4">
                <indicador titulo="Vagas Abertas" indicador="25" bg="bg-dark" color="text-white"></indicador>
            </div>
            <div class="col-4">
                <indicador titulo="Proficionais cadastrados" indicador="30" bg="bg-dark" color="text-white"></indicador>
            </div>
            <div class="col-4">
                <indicador titulo="Usuarios Online" :indicador="usuariosOnline" bg="bg-ligth" color="text-dark"></indicador>
            </div>
        </div>
    </div>
</template>

<script>

import PesquisarVaga from "@/components/comuns/PesquisarVaga.vue"
import Indicador from "@/components/comuns/IndicadorSistema.vue"

export default {
    name: 'HomePage',
    components: {
        PesquisarVaga, Indicador
    },
    data: () => ({
        usuariosOnline: 0
    }),
    methods: {
        getUsuariosOnline() {
            this.usuariosOnline = Math.floor(Math.random() * 100)
        }
    },
    created() {
        setInterval(this.getUsuariosOnline, 1000)
    }
}
</script>

<style scoped>
h1 {
    color: black;
}
</style>