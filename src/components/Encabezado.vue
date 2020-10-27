<template>
    <header>
        <h1><slot></slot></h1>
    </header>
</template>

<script>
export default {
    name:'Encabezado',
}
</script>

<style scoped>
    header {
        background-color: #f77f00;
        padding:20px 0;
    }
    h1 {
        Color:#003049;
        text-align: center;
    }
</style>