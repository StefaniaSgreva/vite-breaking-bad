<template>
  <AppHeader title="Bracking Bad Api"/>
  <main class="container d-flex flex-column align-items-start justify-content-center">
    <AppSelect/>
    <CharacterList :characters="characterList"/>
  </main>
</template>

<script>
import axios from 'axios';
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
    }
  },
  methods:{
    getCharacters(){
      axios.get(this.apiURL).then(
        (res)=>{
          console.log(res.data);
            this.characterList = [...res.data];
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