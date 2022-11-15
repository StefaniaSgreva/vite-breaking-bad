<template>
  <div class="container d-flex justify-content-start p-4">
    <form  class="row row-cols-lg-auto g-3 align-items-center">
      <div class="col-12">
        <label class="visually-hidden" for="selectCategory">Select category</label>
        <select class="form-select" id="selectCategory" v-model="search" @change="changed">
            <option selected value="">Select category</option>
            <option :value="category" v-for="(category,index) in categoryOptions" :key="index">
              {{category}}</option>
        </select>
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
            ],
            search: ''
          }
        },
        methods:{
           changed(){
                console.log(this.search);
            }
        },
    }
</script>

<style lang="scss" scoped>
  select{
    margin-left: 1rem;
    margin-top: 1rem;
  }
</style>