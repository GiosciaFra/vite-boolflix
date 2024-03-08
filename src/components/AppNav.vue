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
<nav class="pt-5 pb-5 d-flex justify-content-between align-items-center text-danger ">
        <div id="logo" class="pt-3" >
            <img src="/public/img/logo-boolflix.png" alt="">
        </div>
         <div id="searchbar">
                <input class="p-1" type="search" v-model="store.searchValue" placeholder="Search movies or series">
                <button class="p-1 border border-none bg-danger text-white " @click="$emit('search')">Search</button>
         </div>
    
</nav>
</template>

<style lang="scss">
@use '../styles/general.scss';

nav {
    height: 70px;
    width: 100%
}

</style>