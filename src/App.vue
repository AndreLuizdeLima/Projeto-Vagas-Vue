<template>
  <div>
    <topo-padrao @alterarTemplate="componente = $event" />    
    <conteudo :conteudo="componente" />
  </div>
</template>

<script>
import Conteudo from '@/components/layouts/LayoutConteudo.vue'
import TopoPadrao from '@/components/layouts/TopoPadrao.vue'

export default {
  name: 'App',
  components: {
    Conteudo,
    TopoPadrao: TopoPadrao
  },
  data: () => ({
    componente: 'HomePage'
  }),
  methods: {
  }
}
</script>

<style scoped>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
}
</style>
