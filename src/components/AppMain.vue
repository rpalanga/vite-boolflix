<script>
import {store} from "../store.js";
import AppPlaybill from "./AppPlaybill.vue";
import AppPoster from "./AppPoster.vue"

export default{
    name:"AppMain",

    data(){
        return{
            store
        }
    },
    components:{
        AppPoster,
        AppPlaybill
    }
}

</script>

<template>
    <div class="container">
        <h1>Film:</h1>
        <ul id="film">
            <AppPoster
            v-for="Movie in store.filmlist" :poster="Movie"
            />

        </ul>
        <h1>Series:</h1>
        <ul id="series">
            <AppPlaybill
            v-for="Series in store.serieslist" :playbill="Series"
            />
        </ul>

    </div>


</template>

<style lang="scss">
@use "../styles/newstyle.scss" as *;
#film{
    list-style-type: none;
        display: flex;
        flex-wrap: wrap;
    
        gap: 25px;

        margin-top: 30px;

}
#series{
    list-style-type: none;
        display: flex;
        flex-wrap: wrap;
    
        gap: 25px;

        margin-top: 30px;

}


</style>