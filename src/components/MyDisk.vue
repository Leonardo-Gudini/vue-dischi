<template>
  <div class="music-disk p-3">
    <img class="cover" :src="musicDisk.poster" alt="image cover">
    <h2 class="title mt-3">{{musicDisk.title}}</h2>
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

.music-disk{
    width: calc(99% / 6);
    background-color: #353D47;
    height: 400px;
    .cover{
        width: 100%;
    }
    .author, .year{
        color: gray;
    }
    .author{
        font-weight: bold;
    }
}

</style>