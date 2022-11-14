<template>
  <label for="Select category"></label>
  <select name="Select category" id="Select category" class=" orm-select mb-4 p-2 rounded">
    <option selected>Select category</option>
  </select>
</template>

<script>
    export default {
        name: 'AppSelect'
    }
</script>

<style lang="scss" scoped>
  select{
    margin-left: 1rem;
    margin-top: 1rem;
  }
</style>