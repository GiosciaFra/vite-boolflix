<script>
export default {
    name: 'MovieItem',
    
    props: {
        movie: Object,
    },

    methods: {
        showFlag(){
            return  `https://flagcdn.com/16x12/${this.movie.original_language}.png`
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
    },

}

</script>

<template>   

    <div class=" d-flex flex-column card col-12 col-md-6 col-lg-3 p-0 position-relative border-1 rounded-0 my-card text-white">

        <div class="d-flex img-box">

            <img class="my_img w-100 h-auto" :src="showPosters()" alt="">
        </div>

        <div class="overlay d-flex flex-column gap-3 h-100 w-100">
            <span>{{ movie.title }}</span>
            
            <span>{{ movie.original_title }}</span>
            
            <div class=" d-flex justify-content-center">

                <img class="my_flag" :src="showFlag()" alt="">
            </div>
            
            <div class="d-flex justify-content-center ">
                <i  v-for="star in showRating()" :class="star"></i>
            </div>

            <span class="overflow-auto" >
                {{ movie.overview }}
            </span>
        </div>
    </div>

</template>

<style lang="scss" >
@use '../styles/general.scss' as *;

.my_flag {
    width: 18px;
    height: 14px;
}

.my_img{
    aspect-ratio: 1 / 1.5;
  }
  .overlay {
  position: absolute; 
  bottom: 0; 
  left: 0;
  background: rgba(0, 0, 0, 0.8);
  opacity:0;
  text-align: center;
  padding: 10px;
  cursor: pointer;
//   pointer-events: none;
}
.my-card:hover .overlay {
  opacity: 1;
}
</style>