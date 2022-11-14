<template>
    <header class="p-2">
        <img src="" alt="logo">
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
        display: inline-block;
        padding-left: 1rem;
    }
</style>