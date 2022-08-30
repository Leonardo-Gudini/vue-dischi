<template>
  <div id="app">
    <MyHeader :genreList="genreList" @changeGenre="startSearch"/>
    <MyMain @genreListReady="getGenreList" :genreToSearch="genreToSearch"/>
  </div>
</template>

<script>
import MyHeader from './components/MyHeader.vue';
import MyMain from './components/MyMain.vue';


export default {
  name: 'App',
  components: {
    MyHeader,
    MyMain
},
data(){
  return{
    genreList: [],
    genreToSearch: ""
  }
},
methods:{
  getGenreList(allGenre){
    this.genreList = allGenre;
  },
  startSearch(genreToSearch){
    this.genreToSearch = genreToSearch
  }
}
}
</script>

<style lang="scss">

@import "style/general.scss";
@import "~bootstrap/dist/css/bootstrap.css"


</style>
