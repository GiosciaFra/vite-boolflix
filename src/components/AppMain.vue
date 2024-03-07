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

    

    <div class="pt-4 pb-3 fw-bold fs-5 text-uppercase ">
        Movies
    </div>
    <hr class="p-2 text-black">

    <div class="container">


        <MovieItem v-for="movie in store.movie" :movie="movie"></MovieItem>
    </div>

    <div  class="pt-4 pb-3 fw-bold fs-5 text-uppercase ">
        Series
    </div>

    <hr class="p-2 text-black">
    <div class="container">
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