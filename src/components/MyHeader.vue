<template>
  <header class="d-flex justify-content-between align-items-center px-3">
    <div class="logo-container">
        <img class="logo" src="../assets/logo.png" alt="logo">
    </div>

    <div class="search">
      <select class="form-select" aria-label="Default select example" @change="$emit('changeGenre', 'genreSelected')" v-model="genreSelected">
        <option selected>Seleziona genere</option>
        <option v-for="(genre, index) in genreList" :key="index" :value="genre">{{genre}}</option>
      </select>
    </div>
  </header>
</template>

<script>
export default {
    name: "MyHeader.vue",
    props:{
      genreList: Array,
    },
    data(){
      return{
        genreSelected: ""
      }
    }
};

</script>

<style lang="scss">
    @import "../style/headerStyle.scss";
</style>