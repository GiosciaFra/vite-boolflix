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
        }
    }
}
</script>

<template>
        <div id="card-series" class="container-fluid d-flex flex-row  ">

            <div class="card col-4 ">

                <img :src="showPosters()" alt="">
                <span>{{ serie.name }}</span>

                <span>{{ serie.original_name }}</span>
                <div>
                    
                <img :src="showFlag()" alt="">
            </div>
                <span>{{ serie.vote_average }}</span>

            </div>

        </div>

</template>

<style lang="scss">
@use '../styles/general.scss' as *;

</style>