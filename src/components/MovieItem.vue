<script>
export default {
    name: 'MovieItem',
    
    props: {
        movie: Object,
    },

    methods: {
        showFlag(){
            return 
                `https://flagcdn.com/16x12${this.movie.original_language}.png`
        }, 

        showPosters(){
            return `https://image.tmdb.org/t/p/w342/${this.movie.poster_path}.jpg`
        }
    }
}

</script>

<template>       



<div id="card-movies" class="container-fluid gap-2 d-flex flex-row  ">

    <div class="card col-4 ">

    <img :src="showPosters()" alt="">
    <span>{{ movie.title }}</span>
    
    <span>{{ movie.original_title }}</span>
    
    <img :src="showFlag()" alt="">
    
    <span>{{ movie.vote_average }}</span>
</div>
</div>
</template>

<style lang="scss" >
@use '../styles/general.scss' as *;


</style>