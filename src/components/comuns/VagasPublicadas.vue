<template lang="">
    <div class="card">
        <div class="card-header bg-dark text-white">{{titulo}}</div>
        <div class="card-body">
            <p>{{descricao}}</p>
        </div>
        <div class="card-footer">
            <small class="text-muted">Salario: R$ {{salario}} | Modalidade: {{getModalidade}} | Tipo: {{getTipo}} | Publicação {{publicacao}}</small>
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
                if(p < 0) return false
                return true
            }
        },
        modalidade: String,
        tipo: String,
        publicacao: String
    },
    computed: {
        getModalidade() {
            switch(this.modalidade) {
                case '1': return 'Home Office'
                case '2': return 'Presencial'
            }
            return ''
        },
        getTipo() {
            switch(this.tipo) {
                case '1': return 'CLT'
                case '2': return 'PJ'
            }
            return ''
        }
    }
} 
</script>
<style></style>
