<script>
export default {
    name: 'MovieItem',
    
    props: {
        movie: Object,
    },
}

</script>

<template>       
<div id="movies">
    <span>{{ movie.title }}</span>
    <br>
    <span>{{ movie.original_title }}</span>
    <br>
    <span>{{ movie.original_language }}</span>
    <br>
    <span>{{ movie.vote_average }}</span>
</div>
</template>

<style lang="scss">
@use '../styles/general.scss' as *
</style>