<template>
    <div>
        <p>{{titulo}}</p>
        <button @click="atualizarComponente()">Atualizar</button><br>
        <button @click="conteudo = 'home-page'">home</button>
        <button @click="conteudo = 'publicar-vaga'">publicar vaga</button>
        
        <component :is="conteudo" />
        
        <!-- Renderizar de modo dinamico os componentes home e publicar vaga-->
        <!--
        <home-page />
        <publicar-vaga />
        -->
    </div>
</template>

<script>
/* eslint-disable no-unused-labels */

import HomePage from '@/components/views/HomePage.vue';
import PublicarVaga from '@/components/views/PublicarVaga.vue';

export default {
    name: 'ConteudoLayout',
    data: () => ({
        teste2: 'O componente foi criado',
        titulo: 'Componente conteudo',
        conteudo: 'home-page'
    }),
    components: {
        HomePage,
        PublicarVaga
    },
    methods: {
        atualizarComponente() {
            this.titulo += '*'
        }
    },
    beforeCreate(){
        /* validar autenticação */
        console.log('Antes de criar', this.teste2)
    },
    created() {
        console.log('Criado ', this.teste2)
    },
    beforeMount() {
        /* carregar os dados de uma api */
        console.log('antes de montar')
    },
    mounted() {
        console.log('Montado template foi para o dom')
    },
    beforeUpdate() {
        console.log('Antes de atualizar')
    },
    updated() {
        console.log('Atualizado')
    },
    beforeUnmount() {
        console.log('Antes de desmontar')
    },
    unmounted() {
        console.log('desmontado e destruido')
    },
    /* 
    errorCaptured() {
        console.log('captura de um erro')
    }, 
    renderTracked() {
        console.log('Re-renderização rastreada')
    },
    renderTriggered() {
        console.log('Re-renderização ativada')
    },
    activated() {
        console.log('Componente ativado')
    },
    deactivated() {
        console.log('componente desativado')
    }
    */
}
</script>

<style scoped></style>