<script>
export default {
    name: 'AppCard',
    
    props: {
        movie: Object,
    },

    methods: {
        showFlag(){
            let flag = this.movie.original_language;
            switch(this.movie.original_language) {

                case "ja":
                    flag = "jp";
                
                case "en":
                    flag = "us";

                case "cs":
                    flag = "cz"

                case "uk":
                    flag = "gb"

                case "hi":
                    flag = "in"

                 case "sv":
                    flag = "se"

                case "ko":
                    flag = "kr";
                        
                case "da":
                    flag = "dk";
                            
                case "zh":
                    flag = "cn";
                    default:
         }
            return  `https://flagcdn.com/16x12/${flag}.png`
        }, 

        showPosters(){
            if(this.movie.poster_path != null) {
        
            return `https://image.tmdb.org/t/p/w342/${this.movie.poster_path}.jpg`
        }else{
        return `/img/fallback.webp`
    }
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

        <div class="d-flex ">

            <img class="my_img w-100 h-auto" :src="showPosters()" alt="">
        </div>

        <div class="overlay d-flex flex-column gap-1 h-100 w-100">

            <div class=" d-flex gap-2">
                    <strong>Title:</strong>
                    <span>{{ movie.title ? movie.title : movie.name }}</span>
                    
                </div>
                <div class=" d-flex gap-2">

                    <strong>Original title:</strong>
                    <span>{{ movie.original_title ? movie.original_title : movie.original_name }}</span>
                </div>

            <div class=" d-flex align-items-center gap-2 ">

                <strong>Original language:</strong>
                <img class="my_flag" :src="showFlag()" alt="">
            </div>
            
            <div class="d-flex  align-items-center gap-2">
                <strong>Rating:</strong>
                <i  v-for="star in showRating()" :class="star" class=" text-warning "></i>
            </div>

            <strong>Overview:</strong>
            <div class="overflow-auto" >
               {{ movie.overview }}
            </div>
        </div>
    </div>

</template>

<style lang="scss" >
@use '../styles/general.scss' as *;


.my_img{
    aspect-ratio: 1 / 1.5;
}
.my_flag {
    width: 18px;
    height: 14px;
}
  .overlay {
  position: absolute; 
  bottom: 0; 
//   left: 0;
right: 0;
  background: rgba(0, 0, 0, 0.9);
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