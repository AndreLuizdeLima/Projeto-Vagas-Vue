<template lang="">
    <div class="card">
        <div class="card-header bg-dark text-white">
            <div class="row">
                <div class="col d-flex justify-content-between">
                    <div>
                        {{titulo}}
                    </div>
                    <div>
                    <div class="form-check form-switch">
                        <input class="form-check-input" type="checkbox" v-model="favoritada">
                        <label class="form-check-label">Favoritar</label>
                        </div>
                    </div>
                </div>
            </div>


        </div>
        <div class="card-body">
            <p>{{descricao}}</p>
        </div>
        <div class="card-footer">
            <small class="text-muted">Salario: R$ {{salario}} | Modalidade: {{getModalidade}} | Tipo: {{getTipo}} |
                Publicação {{getPublicacao}}</small>
        </div>
    </div>
</template>
<script>
export default {
    name: 'VagasPublicadas',
    /*props: ['titulo',
        'descricao',
        'salario',
        'modalidade',
        'tipo',
        'publicacao'],*/
    data: () => ({
        favoritada: false
    }),
    props: {
        titulo: {
            type: String,
            required: true,
        },
        descricao: {
            type: String,
            //default: 'Descrição ñão informado'
            default() {
                return '*'.repeat(20)
            }
        },
        salario: {
            type: [Number, String],
            required: true,
            validator(p) {
                if (p < 0) return false
                return true
            }
        },
        modalidade: String,
        tipo: String,
        publicacao: String
    },
    computed: {
        getModalidade() {
            switch (this.modalidade) {
                case '1': return 'Home Office'
                case '2': return 'Presencial'
            }
            return ''
        },
        getTipo() {
            switch (this.tipo) {
                case '1': return 'CLT'
                case '2': return 'PJ'
            }
            return ''
        },
        getPublicacao() {
            let dataPubli = new Date(this.publicacao)
            return dataPubli.toLocaleDateString('pt-BR')
        }
    },
    methods: {
        dispararEvento() {
            this.emitter.emit('eventoGlobal1', 'teste captura evento')
        }
    },
    watch: {
        favoritada(valorNovo) {
            if (valorNovo) {
                this.emitter.emit('favoritarVaga', this.titulo)
            } else {
                this.emitter.emit('desfavoritarVaga', this.titulo)
            }
        }
    }
} 
</script>
<style></style>