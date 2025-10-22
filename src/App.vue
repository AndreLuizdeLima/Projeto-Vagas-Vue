<template>
  <div>
    <vagas-favoritas></vagas-favoritas>

    <topo-padrao @alterarTemplate="componente = $event" />

    <alerta-pop-up v-if="exibirAlerta">
      <template v-slot:titulo>
        <h5>Titulo alerta</h5>
      </template>

      <template v-slot:descricao>
        <p>conteudo</p>
      </template>
    </alerta-pop-up>
    
    <conteudo :conteudo="componente" />
  </div>
</template>

<script>
import Conteudo from '@/components/layouts/LayoutConteudo.vue'
import TopoPadrao from '@/components/layouts/TopoPadrao.vue'
import VagasFavoritas from './components/comuns/VagasFavoritas.vue'
import AlertaPopUp from './components/comuns/AlertaPopUp.vue'

export default {
  name: 'App',
  components: {
    Conteudo,
    TopoPadrao: TopoPadrao,
    VagasFavoritas,
    AlertaPopUp
  },
  data: () => ({
    componente: 'HomePage',
    exibirAlerta: false
  }),
  methods: {
  },
  mounted() {
    this.emitter.on('alerta', () => {
      this.exibirAlerta = true
      setTimeout(() => this.exibirAlerta = false, 4000)
    })
  }
}
</script>

<style scoped>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
}
</style>
