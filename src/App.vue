<script>
import axios from "axios";
import {store} from "./store.js"

export default {
  data(){
    return{
      store
    }
  },
  created(){
    let urlMovie="https://api.themoviedb.org/3/search/movie?api_key=7795c78756e9ca816b8f86914a27cd4c&"

    axios.get(urlMovie).then(res =>{
      console.log(res.results)
    })
  }
}




</script>

<template>
  
</template>

<style lang="scss">
@use "./styles/newstyle.scss" as *;


</style>
