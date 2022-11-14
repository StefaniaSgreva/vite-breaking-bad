<template>
    
    <div class="card-container">
        <img :src="character.img" :alt="character.name">
        <h2>{{character.name}}</h2>
        <h3>{{character.category}}</h3>
        <h4>{{character.status}}</h4>
    </div>
    
</template>

<script>
    export default {
        name: 'CardComponent',
        props: {
            character: Object
        }
    }
</script>

<style lang="scss" scoped>
 @use '../assets/styles/partials/variables' as *;

    .card-container{
        background-color: $bg-color;
        padding: 1rem;
        margin-top: 1rem;
        height: 500px;
        

        img{
            width: 100%;
        }
        h2{
            text-transform: uppercase;
            font-size: 18px;
            font-weight: 600;
            text-align: center;
            margin: 1.5rem 0;
        }
        h3,
        h4{
            color: $color-gray;
            text-align: center;
        }
        h3{
            font-size: 18px;
        }
        h4{
            font-size: 16px;
        }
    }
</style>