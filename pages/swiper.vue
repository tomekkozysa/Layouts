<template>
  <div class="container">
      <swiper class="swiper" :options="swiperOptions">
            <swiper-slide :key="banner" v-for="banner in banners"><img :src="banner"></swiper-slide>
      </swiper>     
  </div>
</template>

<script>
import { Swiper, SwiperSlide, directive } from 'vue-awesome-swiper'
// import 'swiper/css/swiper.css'

// Elm short thick bit.jpg
// Oak trestle console 4.jpg


// PHOTO-2021-02-13-12-14-07_3.jpg
// PHOTO-2021-02-13-12-14-07_4.jpg
// PHOTO-2021-02-13-12-14-07_5.jpg
// PHOTO-2021-02-13-12-14-07_6.jpg
// PHOTO-2021-02-13-12-14-07_7.jpg
// PHOTO-2021-02-13-12-14-07_8.jpg
// PHOTO-2021-02-13-12-14-07_9.jpg
// PHOTO-2021-02-13-12-14-07.jpg
// PHOTO-2021-02-13-13-17-07_7.jpg
// PHOTO-2021-02-13-13-17-07_8.jpg
export default {
    components: {
    Swiper,
    SwiperSlide
  },
  directives: {
    swiper: directive
  },
    data(){
        return{
            banners: [ 
                '/img/rmc_002.jpg', 
                '/img/rmc_003.jpg', 
                '/img/rmc_004.jpg', 
                '/img/rmc_005.jpg', 
                '/img/rmc_006.jpg', 
                '/img/rmc_007.jpg', 
                '/img/rmc_008.jpg', 
                '/img/rmc_009.jpg', 
                '/img/rmc_0010.jpg', 
                '/img/rmc_0011.jpg', 
                '/img/rmc_0012.jpg', 
                '/img/rmc_0013.jpg', 
                '/img/rmc_0014.jpg', 
                '/img/rmc_0015.jpg', 
                '/img/rmc_0016.jpg', 
                '/img/rmc_0017.jpg', 
            
            
            ],
            swiperOptions: {
                loadPrevNext:true,
                        //    crossFade: true,
                        
                loop: true,
                slidesPerView: 'auto',
                freeMode: false,
                freeModeSticky: true,
                centeredSlides: true,
                spaceBetween: 30,
                grabCursor: true,           
                // mousewheel: true,
                // resistanceRatio:0,
                cssMode:true,
                keyboard: {
    enabled: true,
    onlyInViewport: false,
  },
            }
        }
        
           
    },
    methods:{

    },
    mounted(){}

        
}
</script>

<style>

@import 'https://cdn.jsdelivr.net/npm/swiper@5.3.6/css/swiper.min.css';


body {
  font-family:
    'Quicksand',
    'Source Sans Pro',
    -apple-system,
    BlinkMacSystemFont,
    'Segoe UI',
    Roboto,
    'Helvetica Neue',
    Arial,
    sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

/* 

.container *{
    box-sizing: border-box;
}


.swiper-container {
    margin-left: auto;
    margin-right: auto;
    position: relative;
    overflow: hidden;
    list-style: none;
    padding: 0;
    z-index: 1;
}

.swiper-wrapper {
    position: relative;
    width: 100%;
    height: 100%;
    z-index: 1;
    display: flex;
    transition-property: transform;
    box-sizing: content-box;
    will-change: transform;
    
}



.swiper-slide {
    flex-shrink: 0;
    width: 100%;
    width:auto;
    height: 100%;
    position: relative;
    transition-property: transform;
     will-change: transform;
    padding:20px;
}


 */


.swiper-wrapper {
    transition-timing-function:cubic-bezier(0, 0, 0, 1);
    will-change: transform;
    
}
.swiper{
    margin-top:5vh;
    user-select: none;
}


.swiper-slide{
    display: flex;
    align-items: center;
    justify-content: center;
    
    box-sizing: border-box;
    height:90vh;
    
    -webkit-transform: translate3d(0, 0, 0);
    


}


.swiper-slide img{
    display: block;
    max-width:90%;
    width:auto;
    max-height:100%;
}
/* 
.swiper-slide{
    transition:transform .25s ease-out
}

.swiper-slide-duplicate-active,
.swiper-slide-active{
    transform:translateX(0)
}

.swiper-slide-next{
    transform:translateX(25%)
}
.swiper-slide-prev{
    transform:translateX(-25%)
} */
</style>
