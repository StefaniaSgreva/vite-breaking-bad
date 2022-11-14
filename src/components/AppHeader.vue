<template>
    <header class="d-flex justify-content-start align-items-center">
        <img src="../assets/img/logo-png.PNG" alt="logo">
        <h1 class="mb-4">{{title}}</h1>
    </header>
</template>

<script>
    export default {
        name: 'AppHeader',
        props:{
            title: String
        }
    }
    
</script>

<style lang="scss" scoped>
    h1{
        font-weight: 600;
        padding-top: 22px;
    }
    img{
        width: 80px;
    }
</style>