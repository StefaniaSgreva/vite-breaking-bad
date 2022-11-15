<template>
  <AppHeader title="Bracking Bad Api"/>
  <main class="container d-flex flex-column align-items-start justify-content-center">
    <AppSelect />
    <CharacterList />
  </main>
</template>

<script>
import axios from 'axios';
import AppHeader from './components/AppHeader.vue';
import AppSelect from './components/AppSelect.vue';
import CharacterList from './components/CharacterList.vue';

import {store} from './store';

  export default {
      components: {
      AppHeader,
      AppSelect,
      CharacterList
      },
      data(){
        return{
          store,
          endPoint: 'characters',
        }
      },
      methods:{
        getCharacters(){
          store.loading = true;
          const apiurl = store.apiURL + this.endPoint;
          axios.get(apiurl).then(
              (res)=>{
                // console.log(res.data);
                store.characterList = res.data;
                store.loading = false;
              }
            ).catch((error)=>{
              store.loading = false;
              store.errormessage = error.message;   
            })
        }
      },
      created(){
        this.getCharacters();
      }
  }
</script>

<style lang="scss" scoped>

</style>