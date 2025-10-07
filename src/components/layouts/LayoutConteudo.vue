<template>
    <div>
        <p>Conteudo</p>
        <home-page />
        <publicar-vaga />
    </div>
</template>

<script>
import HomePage from '@/components/views/HomePage.vue';
import PublicarVaga from '@/components/views/PublicarVaga.vue';

export default {
    name: 'ConteudoLayout',
    components: {
        HomePage,
        PublicarVaga
    }
}
</script>

<style scoped></style>