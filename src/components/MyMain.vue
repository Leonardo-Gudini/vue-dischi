<template>
  <main class="p-3">

        <div class="container d-flex flex-wrap justify-content-center">

            <MyDisk class="m-2 text-center" v-for="(musicDisk, index) in diskFiltered" :key="index" :musicDisk="musicDisk"/>

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
            musicDiskList: [],
            genreList : []
        };
    },
    props: {
        genreToSearch: String
    },
    computed:{
        diskFiltered(){
            if (this.genreToSearch == ""){
                return this.musicDiskList;
            } else {
                const arrayDisk = this.musicDiskList.filter(disk => {
                    if (disk.genre == this.genreToSearch){
                        return true;
                    } else{
                        return false;
                    }
                });

                return arrayDisk
            }
        }
    },
    created() {
        this.getMusicDiskList();
    },
    methods: {
        getMusicDiskList() {
            axios.get("https://flynn.boolean.careers/exercises/api/array/music")
            .then(res => {
            this.musicDiskList = res.data.response;
            console.log(res.data.response)

            this.musicDiskList.forEach( disk => {
                if(!this.genreList.includes(disk.genre)) {
                    this.genreList.push(disk.genre)
                }
            });

            this.$emit("genreListReady", this.genreList);
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