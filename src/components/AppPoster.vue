<script>
import {store} from "../store.js";

export default{
    name:"AppPoster",

    data(){
        return{
            store
        }
    },
    props:{
        poster:Object,
    },
    methods:{
        ShowPoster(currentPoster){
            return `https://image.tmdb.org/t/p/w342${currentPoster}`
        }
    }

}

</script>

<template>
   
   <li id="element">
    <img :src="ShowPoster(poster.poster_path)" alt="">
    <h3>{{ poster.title }}</h3>
    <span>{{ poster.original_language }}</span>
    <small>{{ poster.vote_count }}</small>

    


   </li>

</template>

<style lang="scss">
@use "../styles/newstyle.scss" as *;

#element{
    display: flex;
    flex-direction: column;
    gap: 20px;

    width: calc(100% / 5 - 25px / 5 * 4);

    text-align: center;
    text-transform: uppercase;
    img{
        width: 100%;
        object-fit: cover;
        object-position: center;
        
    }
}


</style>