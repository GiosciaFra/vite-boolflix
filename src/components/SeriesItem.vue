<script>
export default {
    name: 'SeriesItem',
    
    props: {
        serie: Object,
    },

    methods: {
        showFlag(){
            return 
                `https://flagcdn.com/16x12/${this.serie.original_language}.png`
        }, 

        showPosters(){
            return `https://image.tmdb.org/t/p/w342${this.serie.poster_path}`
        },

        showRating(){
            const rating = Math.round(this.serie.vote_average / 2);

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
        <div id="card-series" class="container-fluid d-flex flex-row w-25">

            <div class="card ">

                <img :src="showPosters()" alt="">
                <span>{{ serie.name }}</span>

                <span>{{ serie.original_name }}</span>
                
                <img :src="showFlag()" alt="">

                <div class="d-flex">
                    <i  v-for="star in showRating()" :class="star"></i>
                </div>

        </div>
        </div>

</template>

<style lang="scss">
@use '../styles/general.scss' as *;

</style>