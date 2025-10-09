<template>
    <div>
        <p>home</p>
    </div>
</template>

<script>
export default {
    name: 'HomePage',
    activated() {
        console.log('Componente ativado')
    },
    deactivated() {
        console.log('componente desativado')
    },
        beforeUnmount() {
        console.log('Antes de desmontar')
    },
    unmounted() {
        console.log('desmontado e destruido')
    }
}
</script>

<style scoped>
h1 {
    color: black;
}
</style>