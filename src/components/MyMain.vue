<template>
  <main>

        <div class="my-container container text-center">
            <div class="row">
                <div class="col">ciao</div>
            </div>
        </div>
  </main>
</template>

<script>

import axios from "axios";

export default {
    name: "MyMain",

    data() {
       return{
         musicDiskList : []
       }
    },

    created(){

        axios.get("https://flynn.boolean.careers/exercises/api/array/music")
        .then( response => {
            this.musicDiskList = response.data.response;
        })
    }
}
</script>

<style>

@import "../style/mainStyle.scss"

</style>