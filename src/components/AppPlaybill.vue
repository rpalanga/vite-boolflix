<script>
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
        <span>{{ playbill.original_language }}</span>
        <small>{{ playbill.vote_count }}</small>



    </li>

</template>

<style lang="scss">
@use "../styles/newstyle.scss" as *;

#element2 {
    display: flex;
    flex-direction: column;
    gap: 20px;

    width: calc(100% / 5 - 25px / 5 * 4);

    text-align: center;
    text-transform: uppercase;

    img {
        width: 100%;
        object-fit: cover;
        object-position: center;

    }
}
</style>