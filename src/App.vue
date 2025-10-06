<template>
  <div>
    <Topo />
    <Conteudo />
  </div>
</template>

<script>
import Conteudo from './components/layouts/LayoutConteudo.vue'
import Topo from './components/layouts/LayoutTopo.vue'

export default {
  name: 'App',
  components: {
    Conteudo,
    Topo
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
