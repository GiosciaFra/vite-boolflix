<script>

import {store} from './store';
import AppNav from './components/AppNav.vue';
import AppMain from './components/AppMain.vue'
import axios from 'axios'; 

export default {
  components: {
    AppNav,
    AppMain,
  },

  data() {
    return {
      store,
    }
  },
  
//   created() {
//     axios.get("https://api.themoviedb.org/3/search/movie?api_key=98149095997580a258be6c4d79203beb&query=ritorno+al+futuro").then(res => {this.store.movies 
//       = res.data.result;
//       console.log(res.data.result);
// });
// },

methods: {
  searchMovies() {
    axios.get("https://api.themoviedb.org/3/search/movie?api_key=98149095997580a258be6c4d79203beb&query=" + this.store.searchValue)
    .then(res => 
    {
      // console.log(res.data.result)
      // console.log(this.store.searchValue);
      this.store.movies = res.data.results;
    });
    
  },
},
}




</script>

<template>
    <div class="container">
      <AppNav @click="searchMovies()"></AppNav>
        <AppMain></AppMain>
    </div>
</template>

<style lang="scss">
@use './styles/general.scss' as *
</style>
