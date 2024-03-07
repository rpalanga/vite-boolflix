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
    <h6>{{ poster.original_title }}</h6>
    <span>{{ poster.original_language }}</span>
    <small>{{ poster.vote_count }}</small>

    


   </li>

</template>

<style lang="scss">
@use "../styles/newstyle.scss" as *;

#element{
    display: flex;
    flex-direction: column;
    // gap: 20px;

    width: calc(100% / 3);

    text-align: center;
    text-transform: uppercase;
    h6{
        color: red;
    }
    img{
        width: 100%;
        // height: 270px;
        height: 490px;
        object-fit: cover;
        object-position: center;
        border: 1px solid rgba($color: #ffffff, $alpha: 0.5);
        
    }
}


</style>