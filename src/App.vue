<template>
  <div>
    <topo-padrao />
    <button @click="desmontar()">Desmontar componente conteudo</button>
    <conteudo v-if="visibilidade" />
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
    visibilidade: true
  }),
  methods: {
    desmontar(){
      this.visibilidade = false
    }
  }
}
</script>

<style scoped>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
}
</style>
