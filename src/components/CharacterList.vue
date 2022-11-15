<template>
    <div class="ch-list-container">
        <div class="loading" v-if="store.loading">Loading data</div>
        <div class="found">Found {{}} characters</div>

        <div class="row row-cols-lg-5 row-cols-md-4 row-cols-sm-6" v-if="!store.loading">
            <div class="col" v-for="(item,index) in store.characterList" :key="item.id">
                <CardComponent :character="item"/>
            </div>
        </div>

    </div>
    
</template>

<script>
import {store} from '../store'
import CardComponent from './CardComponent.vue';

    export default {
    name: "CharacterList",
    // props: ["characters", "loading"],
    components: { CardComponent },
    data(){
        return{
            store,
        }
    }
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
        margin: 0 5px;
    }
</style>