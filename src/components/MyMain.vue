<template>
  <main class="p-3">

        <div class="container d-flex flex-wrap justify-content-center">

            <MyDisk class="m-2 text-center" v-for="(musicDisk, index) in musicDiskList" :key="index" :musicDisk="musicDisk"/>

        </div>
  </main>
</template>

<script>

import axios from "axios";
import MyDisk from "./MyDisk.vue";

export default {
    name: "MyMain",
    components: {
    MyDisk,
},
    data() {
        return {
            musicDiskList: []
        };
    },
    created() {
        this.getMusicDiskList();
    },
    methods: {
        getMusicDiskList() {
            let that = this;
            axios.get("https://flynn.boolean.careers/exercises/api/array/music")
            .then(response => {
            that.musicDiskList = response.data.response;
            console.log(response.data.response)
        })
        .catch(error => {
            console.log(error)
        })
        }
    },
}
</script>

<style lang="scss">

@import "../style/mainStyle.scss"

</style>