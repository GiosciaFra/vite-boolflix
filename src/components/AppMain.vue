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

    

<div class="container">
    <div>
        Movies
    </div>
    <MovieItem v-for="movie in store.movie" :movie="movie"></MovieItem>
<br>
    <div>
        Series
    </div>

    <SeriesItem v-for="serie in store.serie" :serie="serie"></SeriesItem>
</div>
</template>

<style lang="scss" scoped>
@use '../styles/general.scss';


</style>