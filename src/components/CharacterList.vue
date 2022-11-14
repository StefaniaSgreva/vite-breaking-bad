<template>
    <div class="ch-list-container">
        <div class="found">Found...</div>

        <div class="row row-cols-lg-5 row-cols-md-4 row-cols-sm-6">
        <div class="col">
            ciao
        </div>
    </div>

    </div>
    
</template>

<script>
    export default {
        name: 'CharacterList'
    }
</script>

<style lang="scss" scoped>
 @use '../assets/styles/partials/variables' as *;
 

    .ch-list-container{
        background-color: $bg-container-color;
        padding: 2rem;
        width: 100%;

    }
     .found{
        background-color: $color-dark;
        padding: 1rem;
        font-weight: 600;
    }
    .row{
        background-color: $bg-container-color;
      
    }
</style>