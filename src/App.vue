<template>
  <AppHeader title="Bracking Bad Api"/>
  <main class="container d-flex flex-column align-items-start justify-content-center">
    <AppSelect/>
    <CharacterList/>
  </main>
</template>

<script>
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

  },
  created(){
    
  }
}
</script>

<style lang="scss" scoped>

</style>