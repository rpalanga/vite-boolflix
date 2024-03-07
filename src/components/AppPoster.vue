<script>
import { store } from "../store.js";

export default {
    name: "AppPoster",

    data() {
        return {
            store
        }
    },
    props: {
        poster: Object,
    },
    methods: {
        ShowPoster(currentPoster) {
            return `https://image.tmdb.org/t/p/w342${currentPoster}`
        }

        // getFleg(currentFlag){
        //     if()
        // }
    }


}

</script>

<template>

    <li id="element" >
        <img :src="ShowPoster(poster.poster_path)" alt="">
        <div class="overlay card" >
            <h3>{{ poster.title ? poster.title : poster.name }}</h3>
            <h6>{{ poster.original_title ? poster.original_title : poster.original_name }}</h6>
            <span>{{ poster.original_language }}</span>
            <small>{{ poster.vote_count }}</small>

        </div>




    </li>

</template>

<style lang="scss">
@use "../styles/newstyle.scss" as *;

#element {
    display: flex;
    flex-direction: column;
    // gap: 20px;

    width: calc(100% / 3);

    text-align: center;
    text-transform: uppercase;
    position: relative;
    transition: all 0.5s ease-in-out;





    h6 {
        color: red;
    }

    img {
        width: 100%;
        // height: 270px;
        height: 490px;
        object-fit: cover;
        object-position: center;
        border: 1px solid rgba($color: #ffffff, $alpha: 0.3);
        

    }
}
.card{
    display: flex;
    flex-direction: column;
}

.overlay {
    position: absolute;
    
    bottom: 0;
    background: rgb(0, 0, 0);
    background: rgba(0, 0, 0, 0.8);
    /* Black see-through */
    color: #f1f1f1;
    width: 100%;
    transition: .5s ease;
    opacity: 0;
    color: white;
    font-size: 20px;
    padding: 20px;
    text-align: center;
    height: 100%;
}

li:hover .overlay {
    opacity: 1;

}
li:hover{
    transform: scale(1.2);

    z-index: 1;
}
</style>