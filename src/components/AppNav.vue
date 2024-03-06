<script>
import {store} from "../store.js";

export default{
    name:"AppNav"
}

</script>

<template>
    <div class="container-fluid">

        <h1>Boolflix</h1>
        <label id="search-bar" for="">
            <input type="text" name="" id="">
            <button>Cerca</button>

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
        font-size: 40px;
        margin-left: 15px;
    }

    #search-bar{
        margin-right: 20px;
    }
}

</style>