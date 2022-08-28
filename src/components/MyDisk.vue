<template>
  <div class="music-disk">
    <img class="cover" :src="musicDisk.poster" alt="image cover">
    <h2 class="title">{{musicDisk.title}}</h2>
    <div class="author">{{musicDisk.author}}</div>
    <div class="year">{{musicDisk.year}}</div>
  </div>
</template>

<script>
export default {
    name: "MyDisk",

    props:{
        musicDisk: Object
    }
}
</script>

<style lang="scss">



</style>