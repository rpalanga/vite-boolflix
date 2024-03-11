<script>
import { store } from "../store.js";

export default {
    name: "AppNav",

    data() {
        return {
            store
        }
    },
    methods: {
        // selectGeneres() {
        //     https://api.themoviedb.org/3/genre/movie/list?api_key=7795c78756e9ca816b8f86914a27cd4c
        //     let urlCard = "https://db.ygoprodeck.com/api/v7/cardinfo.php?num=100&offset=0";
        //     //se ho l'archetipo
        //     if (this.store.archtypeSelezionato != "0") {
        //         urlCard = urlCard + "&archetype=" + this.store.archtypeSelezionato

        //     }
        //     console.log(urlCard.store)


        //     axios.get(urlCard)
        //         .then(res => {
        //             console.log(res.data.data)
        //             this.store.cards = res.data.data;

        //             this.load = true;
        //         })


        // }
    },

}

</script>

<template>
    <div class="container-fluid">

        <div class="left-container">
            <h1><small>"the"</small>Boolflix</h1>
            <div class="dropdown">
                <button class="dropbtn">Seleziona la Categoria <i class="fa-solid fa-chevron-down"></i></button>
                <ul class="dropdown-content">
                    <li>Elemento</li>

                </ul>
            </div>

        </div>

        <label id="search-bar" for="">
            <input type="text" name="" id="" placeholder="Cosa vuoi vedere?" v-model="this.store.filmSelected">
            <button @click="$emit(`select`)"><i class="fa-solid fa-magnifying-glass"></i></button>

        </label>

    </div>

</template>

<style lang="scss">
.container-fluid {

    width: 100%;
    background-color: black;

    display: flex;
    justify-content: space-between;
    align-items: center;

    .left-container {
        display: flex;
        align-items: center;
        gap: 30px;

        .dropbtn {
            background-color: rgba(227, 0, 34, 0.5);
            color: white;
            padding: 10px;
            font-size: 15px;
            border: none;
            cursor: pointer;
            border-radius: 15px;

        }

        .dropdown {
            position: relative;
            display: inline-block;
        }

        .dropdown-content {
            display: none;
            position: absolute;
            background-color: #f9f9f9;
            min-width: 160px;
            box-shadow: 0px 8px 16px 0px rgba(0, 0, 0, 0.2);
            z-index: 1;
        }

        .dropdown-content li {
            color: black;
            padding: 10px 15px;
            text-decoration: none;
            display: block;
            list-style-type: none;
        }

        .dropdown-content li:hover {
            background-color: #f1f1f1
        }

        .dropdown:hover .dropdown-content {
            display: block;
        }

        .dropdown:hover .dropbtn {
            background-color: rgb(227, 0, 34);
        }

        h1 {
            color: red;
            font-size: 60px;
            margin-left: 15px;

            small {
                margin-right: 10px;
                font-size: 30px;

            }
        }
    }

    #search-bar {
        margin-right: 20px;
        display: flex;


        input {
            padding: 10px 20px;
            border-radius: 10px;

        }

        button {
            padding: 10px 20px;
            margin-left: 5px;
            border-radius: 10px;
            background-color: crimson;
            font-weight: bolder;
            font-size: 15px;




        }
    }
}
</style>