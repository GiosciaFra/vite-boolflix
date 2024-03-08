<script>
import AppCard from "./AppCard.vue";
import {store} from "../store.js"


export default {
    name: 'AppMain',

    components: {
        AppCard,

    },

    data() {
        return {
            store,
        }
    }
}
</script>

<template>

    

    <div class="py-3 fw-bold fs-2 text-uppercase text-white">
        Movies
    </div>
    <hr class=" border border-4 border-white ">

    <div class="container pt-4">

        <AppCard v-for="movie in store.movie" :movie="movie"></AppCard>

    </div>

    <div  class="pt-5 pb-3 fw-bold fs-2 text-uppercase text-white">
        Series
    </div>

    <hr class="border border-4 border-white">


    <div class="container pt-4 pb-5 ">

        <AppCard v-for="serie in store.serie" :movie="serie"></AppCard>
        
    </div>
</template>

<style lang="scss" scoped>
@use '../styles/general.scss';

.container {
   display: flex;
    flex-flow: row wrap;
}


</style>./AppCard.vue/index.js