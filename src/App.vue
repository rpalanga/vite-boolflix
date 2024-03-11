<script>
import axios from "axios";
import {store} from "./store.js";
import AppNav from "./components/AppNav.vue"
import AppMain from "./components/AppMain.vue"

export default {
  data(){
    return{
      store
    }
  },
  components:{
    AppNav,
    AppMain
  },
  methods:{
    SelectFilm(){
      
  
      axios.get("https://api.themoviedb.org/3/search/movie?api_key=7795c78756e9ca816b8f86914a27cd4c&query=" + this.store.filmSelected).
      then(res =>{
        console.log(res.data.results)
        this.store.filmlist=res.data.results
        
        axios.get("https://api.themoviedb.org/3/search/tv?api_key=7795c78756e9ca816b8f86914a27cd4c&query=" + this.store.filmSelected).
        then(res2 =>{
        console.log(res2.data.results)

          this.store.serieslist=res2.data.results
        })
        
      })

    },
    showCast(){
            axios.get("https://api.themoviedb.org/3/movie/${filmlist}/credits?api_key=7795c78756e9ca816b8f86914a27cd4c").then(res => {
                console.log(res)
            })
        }
  }
}




</script>

<template>
<AppNav @select="SelectFilm()"/>
<AppMain/>


  
</template>

<style lang="scss">
@use "./styles/newstyle.scss" as *;


</style>
