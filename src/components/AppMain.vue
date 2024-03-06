<script>
import AppNav from "./AppNav.vue";
import SearchMovie from "./SearchMovie.vue";
import MovieItem from "./MovieItem.vue";

import axios from 'axios';

export default {
    name: 'AppMain',

    components: {
        AppNav,
        SearchMovie,
        MovieItem,

    },

    data() {
        return {

        }
    }
}
</script>

<template>

    <AppNav></AppNav>
    <SearchMovie></SearchMovie>

<div class="container">
    <MovieItem></MovieItem>
</div>
</template>

<style lang="scss">
@use '../styles/general.scss'
</style>