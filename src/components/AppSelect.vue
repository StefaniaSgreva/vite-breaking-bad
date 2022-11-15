<template>
  <div class="container d-flex justify-content-start py-4">
    <form  class="row row-cols-lg-auto g-3 align-items-center">
      <div class="col-12">
        <label class="visually-hidden" for="selectCategory">Select category</label>
        <select class="form-select" id="selectCategory" v-model="store.search.category" @change="changed">
            <option selected value="">Select category</option>
            <option :value="category" v-for="(category,index) in categoryOptions" :key="index">
              {{category}}</option>
        </select>
      </div>
      <div class="col-12">
          <button type="reset" class="btn btn-dark" @click="resetSearch">Reset</button>
      </div>
    </form>
  </div>
</template>

<script>
import {store} from '../store';
    
  export default {
        name: 'AppSelect',
        data(){
          return{
            store,
            categoryOptions:[
              'Breaking Bad',
              'Better Call Saul'
            ]
          }
        },
        methods:{
           changed(){
                console.log(store.search.category);
                this.$emit('filterchar');
            },
            resetSearch(){
                store.search.category= '';
                this.$emit('filterchar');
            }
        },
  }
</script>

<style lang="scss" scoped>

</style>