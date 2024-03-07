<script>
import MovieItem from "./MovieItem.vue";
import {store} from "../store.js"


export default {
    name: 'AppMain',

    components: {
        MovieItem,

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
    <MovieItem v-for="movie in store.movies" :movie=movie></MovieItem>
</div>
</template>

<style lang="scss">
@use '../styles/general.scss'
</style>