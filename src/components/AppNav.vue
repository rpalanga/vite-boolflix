<script>
import {store} from "../store.js";

export default{
    name:"AppNav",

    data(){
        return{
            store
        }
    }
    
}

</script>

<template>
    <div class="container-fluid">
        
        <h1><small>"the"</small>Boolflix</h1>
        <label id="search-bar" for="" >
            <input type="text" name="" id="" placeholder="Inserisci il film" v-model="this.store.filmSelected">
            <button @click="$emit(`select`)" >Cerca</button>

        </label>
        
    </div>

</template>

<style lang="scss">
.container-fluid{

    width: 100%;
    background-color: black;

    display: flex;
    justify-content: space-between;
    align-items: center;

    h1{
        color: red;
        font-size: 60px;
        margin-left: 15px;
        
        small{
            margin-right: 10px;
            font-size: 30px;

        }
    }

    #search-bar{
        margin-right: 20px;
        
        input{
            padding: 10px;
            border-radius: 10px;

        }
        button{
            padding: 10px;
            margin-left: 5px;
            border-radius: 10px;
            background-color: crimson;
            font-weight: bold;
            
            

        }
    }
}

</style>