<template>
  <AppHeader title="Bracking Bad Api"/>
  <main class="container d-flex flex-column align-items-start justify-content-center">
    <AppSelect @filterchar= "getCharacters"/>
    <CharacterList />
    <div v-if="store.errormessage" class="text-center">
      <h1>Something went wrong!</h1>
      <p>{{store.errormessage}}</p>
    </div>
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
          store.errormessage = '';

          let options = null
          if(store.search.category){
              options = {
                  params:{
                      category: store.search.category, //chiave: valore
                  }
              }
          }

          store.loading = true;
          const apiurl = store.apiURL + this.endPoint;
          axios.get(apiurl, options).then(
              (res)=>{
                // console.log(res.data);
                store.characterList = res.data;
                store.loading = false;
              }
            ).catch((error)=>{
                store.characterList.lenght = 0;
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