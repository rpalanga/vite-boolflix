<!-- <script>
import { store } from "../store.js";

export default {
    name: "AppPlaybill",

    data() {
        return {
            store
        }
    },
    props: {
        playbill: Object,
    },
    methods: {
        ShowPlaybill(currentPlaybill) {
            return `https://image.tmdb.org/t/p/w342${currentPlaybill}`
        }
    }

}

</script>

<template>

    <li id="element2">
        <img :src="ShowPlaybill(playbill.poster_path)" alt="">
        <h3>{{ playbill.name }}</h3>
        <h6>{{ playbill.original_name }}</h6>
        <span>{{ playbill.original_language }}</span>
        <small>{{ playbill.vote_count }}</small>



    </li>

</template>

<style lang="scss">
@use "../styles/newstyle.scss" as *;

#element2 {
    display: flex;
    flex-direction: column;
    // gap: 20px;

    width: calc(100% / 3);

    text-align: center;
    text-transform: uppercase;
    h6{
        color: red;
    }

    img {
        width: 100%;
        height: 490px;
        object-fit: cover;
        object-position: center;
        border: 1px solid rgba($color: #ffffff, $alpha: 0.3);


    }
}
</style> -->