<template>
    <div> 
        <keep-alive>
        <component :is="conteudo" />
        </keep-alive>
    </div>
</template>

<script>
/* eslint-disable no-unused-labels */

import HomePage from '@/components/views/HomePage.vue';
import PublicarVaga from '@/components/views/PublicarVaga.vue';

export default {
    name: 'ConteudoLayout',
    props: {
        conteudo: {
            type: String,
            required: true
        }
    },
    data: () => ({
        teste2: 'O componente foi criado',
        titulo: 'Componente conteudo'
    }),
    components: {
        HomePage,
        PublicarVaga
    },
    methods: {
        atualizarComponente() {
            this.titulo += '*'
        }
    }
}
</script>

<style scoped></style>