<script>
import {store} from '../store.js';
import axios from 'axios';


export default {
    name: 'AppNav',
    
    data() {
        return{
            store,
        }
    }
}
</script>

<template>
<nav class="bg-dark px-2  d-flex justify-content-between align-items-center text-danger ">
        <div id="logo" >
            logo
        </div>
         <div id="searchbar">
                <input type="search" v-model="store.searchValue" placeholder="Search">
                <button @click="$emit('search')">Search movies</button>
         </div>
    
</nav>
</template>

<style lang="scss">
@use '../styles/general.scss';

nav {
    height: 50px;
}

</style>