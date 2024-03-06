<script>
import axios from "axios";
import {store} from "./store.js";
import AppNav from "./components/AppNav.vue"

export default {
  data(){
    return{
      store
    }
  },
  components:{
    AppNav
  },
  created(){
    let urlMovie="https://api.themoviedb.org/3/search/movie?api_key=7795c78756e9ca816b8f86914a27cd4c&query=results"

    axios.get(urlMovie).then(res =>{
      console.log(res.data.results)
    })
  }
}




</script>

<template>
<AppNav/>

  
</template>

<style lang="scss">
@use "./styles/newstyle.scss" as *;


</style>
