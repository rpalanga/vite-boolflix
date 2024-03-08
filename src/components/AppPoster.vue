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

            console.log(currentRate)
            
            // if (currentRate >= 0){
            //     currentRate = <i class="fa-regular fa-star"></i>;
            // }
            // altri esperimenti 
            // let outputStar = [];

            
            // for (let i = currentRate; i >= 1; i--)
            //     output.push('<i class="fa-regular fa-star"></i>&nbsp;');

            
            // if (i == .5){
            //     output.push('<i class="fa-regular fa-star-half-stroke"></i>&nbsp;');
            // } 
                

            // // Fill the empty stars
            // for (let i = (5 - currentRate); i >= 1; i--)
            //     output.push('<i class="fa-regular fa-star-half-stroke"></i>&nbsp;');

            // return outputStar.join('');

            return currentRate;






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
            <span>{{ poster.original_language }}</span>
            <small>

                <i v-for="n in 5" :class="{ 'fa-solid fa-star': n <= getRating(), 'fa-regular fa-star': n > getRating() }"></i>

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
}

.card {
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