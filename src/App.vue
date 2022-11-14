<template>
  <AppHeader title="Bracking Bad Api"/>
  <main class="container d-flex flex-column align-items-start justify-content-center">
    <AppSelect/>
    <CharacterList :characters="characterList" :loading="loading"/>
  </main>
</template>

<script>
import axios from 'axios';
// import { resolveDirective } from 'vue';
import AppHeader from './components/AppHeader.vue';
import AppSelect from './components/AppSelect.vue';
import CharacterList from './components/CharacterList.vue';

export default {
  components: {
  AppHeader,
  AppSelect,
  CharacterList
  },
  data(){
    return{
      apiURL: 'https://www.breakingbadapi.com/api/characters',
      characterList: [],
      loading: false,
    }
  },
  methods:{
    getCharacters(){
      this.loading = true;
      axios.get(this.apiURL).then(
          (res)=>{
            // console.log(res.data);
            this.characterList = [...res.data];
            this.loading = false;
          }
        ).catch((error)=>{
            console.log(error);
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