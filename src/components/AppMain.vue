<script>
import SeriesItem from "./SeriesItem.vue";
import MovieItem from "./MovieItem.vue";
import {store} from "../store.js"


export default {
    name: 'AppMain',

    components: {
        MovieItem,
        SeriesItem

    },

    data() {
        return {
            store,
        }
    }
}
</script>

<template>

    

    <div class="pt-4 pb-3 fw-bold fs-2 text-uppercase text-white">
        Movies
    </div>
    <hr class=" border border-4 border-white ">

    <div class="container pt-4">


        <MovieItem v-for="movie in store.movie" :movie="movie"></MovieItem>
    </div>

    <div  class="pt-5 pb-3 fw-bold fs-2 text-uppercase text-white">
        Series
    </div>

    <hr class="border border-4 border-white">
    <div class="container pt-4">
        <SeriesItem v-for="serie in store.serie" :serie="serie"></SeriesItem>
</div>
</template>

<style lang="scss" scoped>
@use '../styles/general.scss';

.container {
   display: flex;
    flex-flow: row wrap;
}


</style>