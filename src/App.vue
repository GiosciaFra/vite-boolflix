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
  
  created() {
 
},

methods: {
 
  search(){
 
    axios.get("https://api.themoviedb.org/3/search/tv?api_key=98149095997580a258be6c4d79203beb&query=" + this.store.searchValue)
    .then(res => 
    {
       
      this.store.serie = res.data.results;

    });
    axios.get("https://api.themoviedb.org/3/search/movie?api_key=98149095997580a258be6c4d79203beb&query=" + this.store.searchValue)
    .then(res => 
    {
      
      this.store.movie = res.data.results;

    });
    
  }

}
}




</script>

<template>
    <div class="container">
      <AppNav @click="search()"></AppNav>
        <AppMain></AppMain>
    </div>
</template>

<style lang="scss">
@use './styles/general.scss' as *
</style>
