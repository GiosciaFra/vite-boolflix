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
        },

        showRating(){
            const rating = Math.round(this.movie.vote_average / 2);

            const starArray = ['fa-regular fa-star', 
            'fa-regular fa-star',
             'fa-regular fa-star', 
             'fa-regular fa-star,',
              'fa-regular fa-star'];

              for (let i = 0; i < rating; i++) {
                starArray.pop();
                starArray.unshift('fa-solid fa-star');
              }

              return starArray;
        }
    }
}

</script>

<template>   

<div id="card-movies" class="container-fluid gap-2  flex-row w-25  ">

    <div class="card">

    <img :src="showPosters()" alt="">
    <span>{{ movie.title }}</span>
    
    <span>{{ movie.original_title }}</span>
    
    <img :src="showFlag()" alt="">

    <div class="d-flex">
    <i  v-for="star in showRating()" :class="star"></i>
</div>
</div>
</div>
</template>

<style lang="scss" >
@use '../styles/general.scss' as *;


</style>