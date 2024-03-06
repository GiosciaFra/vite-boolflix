<script>
import {store} from "../store.js"

export default {
    name: 'SearchMovie',

    data() {
        return {
            store,
        }
    },
}
</script>

<template>
    <div id="search-bar">
        searchbar
    </div>

</template>

<style lang="scss">
@use '../styles/general.scss' as *;
@use '../styles/variables.scss' as *

</style>