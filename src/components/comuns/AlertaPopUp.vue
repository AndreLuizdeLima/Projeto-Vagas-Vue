<template>
    <div class="alert alert-success" role="alert">
        <slot name="titulo">
            <h3>Titulo mensagem de feedback</h3>
        </slot>
        <hr>
        <slot name="descricao"></slot>
    </div>
</template>

<script>
export default {
    name: 'AlertaPopUp'
}
</script>

<style></style>