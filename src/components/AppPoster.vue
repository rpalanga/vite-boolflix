<script>
import { store } from "../store.js";

export default {
    name: "AppPoster",

    data() {
        return {
            store,
        }
    },
    props: {
        poster: Object,
    },
    methods: {
        ShowPoster(currentPoster) {
            return `https://image.tmdb.org/t/p/w342${currentPoster}`
        },

        getRating(score) {
            let currentRate = Math.round((this.poster.vote_average / 2));

            // console.log(currentRate)

            return currentRate;

        },
        getFlag() {
            let currentFlag = this.poster.original_language;

            switch (this.poster.original_language) {
                case "ja":
                    currentFlag = "jp";
                    break;
                case "ko":
                    currentFlag = "kr";
                    break;
                case "en":
                    currentFlag = "us";
                    break;
                case "zh":
                    currentFlag = "cn";
                    break;
                case "da":
                    currentFlag = "dk";
                    break;
                case "cs":
                    currentFlag = "cz"
                    break;
                case "uk":
                    currentFlag = "gb"
                    break;
                case "sv":
                    currentFlag = "se"
                    break;
                default:
            }

            return `https://flagcdn.com/16x12/${currentFlag}.png`


        }
        
    }


}

</script>

<template>

    <li id="element">
        <img :src="ShowPoster(poster.poster_path)" alt="">
        <div class="overlay card">
            <h3>{{ poster.title ? poster.title : poster.name }}</h3>
            <h5>{{ poster.original_title ? poster.original_title : poster.original_name }}</h5>
            <div id="container-flag">
                <img :src="getFlag(poster.original_language)" alt="" id="Flag">

            </div>
            <small>

                <i v-for="n in 5"
                    :class="{ 'fa-solid fa-star': n <= getRating(), 'fa-regular fa-star': n > getRating() }"></i>

            </small>
            <h6>Plot:</h6>
            <hr>
            <p>{{ poster.overview }}</p>

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





    h5 {
        color: red;
    }

    h6 {
        text-align: left;
        margin-bottom: 5px;
    }

    img {
        width: 100%;
        // height: 270px;
        height: 490px;
        object-fit: cover;
        object-position: center;
        border: 1px solid rgba($color: #ffffff, $alpha: 0.3);


    }

    hr {
        margin-bottom: 10px;
    }

    p {
        font-size: small;
        text-transform: capitalize;
        text-align: left;

    }
    .fa-solid{
        color: rgb(227, 0, 34);
    }
}

.card {
    display: flex;
    flex-direction: column;

    #container-flag {
        display: flex;
        justify-content: center;

        #Flag {
            width: 30px;
            height: 15px;
            object-fit: cover;
        }
    }


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
    overflow: scroll;
    


}

li:hover .overlay {
    opacity: 1;

}

li:hover {
    transform: scale(1.2);

    z-index: 1;
}
</style>