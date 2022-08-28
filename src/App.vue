<template>
  <div id="app">
    <MyHeader/>
    <MyMain/>
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
}
}
</script>

<style lang="scss">

@import "style/general.scss";
@import "~bootstrap/dist/css/bootstrap.css"


</style>
