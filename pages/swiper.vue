<template>
  <div class="container">
    <!-- <div class="swiper-nav">    </div> -->
        <div class="swiper-prev">
            <svg width="24" height="24" xmlns="http://www.w3.org/2000/svg" fill-rule="evenodd" clip-rule="evenodd"><path d="M2.117 12l7.527 6.235-.644.765-9-7.521 9-7.479.645.764-7.529 6.236h21.884v1h-21.883z"/></svg>
        </div>
        <div class="swiper-next">

            <svg width="24" height="24" xmlns="http://www.w3.org/2000/svg" fill-rule="evenodd" clip-rule="evenodd"><path d="M21.883 12l-7.527 6.235.644.765 9-7.521-9-7.479-.645.764 7.529 6.236h-21.884v1h21.883z"/></svg>

        </div>
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
                // slidesPerView: 'auto',
                freeMode: true,
                freeModeSticky: true,
                centeredSlides: true,
                spaceBetween: 30,
                grabCursor: true,           
                mousewheel: true,
                // resistanceRatio:0,
                speed:1000,
                cssMode:true,
                keyboard: {
                    enabled: true,
                    onlyInViewport: false,
                },
                navigation: {
                    nextEl: '.swiper-next',
                    prevEl: '.swiper-prev',
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

/* @import 'https://cdn.jsdelivr.net/npm/swiper@5.3.6/css/swiper.min.css'; */



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
.container{
    position:relative;
}
.swiper-nav{
    position:absolute;
    top:0;
    left:0;
    z-index:1000;
    display: flex;
    height: 90vh;
    width:100vw;
    justify-content: space-between;
}
.swiper-next,
.swiper-prev{
    width:10%;
    height:90vh;
    /* background: pink; */
    cursor: pointer;
    position:absolute;
    top:0;
    left:0;
    z-index:1000;
    display: flex;
    align-items: center;
    justify-content: center;
}
.swiper-next{
    right:0;
    left:auto;
}

.swiper-next svg{
    transform: translateX(-20px);
    opacity:0;
    transition: transform .2s, opacity .1s;    
}
.swiper-next:hover svg{
    transform: translateX(0px);
    opacity:1;
}
.swiper-prev svg{
    transform: translateX(20px);
    opacity:0;    
    transition: transform .2s, opacity .1s;    
}
.swiper-prev:hover svg{
    transform: translateX(0px);
    opacity:1;
}

.swiper-container {
  margin-left: auto;
  margin-right: auto;
  position: relative;
  overflow: hidden;
  list-style: none;
  padding: 0;
  /* Fix of Webkit flickering */
  z-index: 1;
}
.swiper-container-vertical > .swiper-wrapper {
  flex-direction: column;
}
.swiper-wrapper {
  position: relative;
  width: 100%;
  height: 100%;
  z-index: 1;
  display: flex;
  transition-property: transform;
  box-sizing: content-box;
}
.swiper-container-android .swiper-slide,
.swiper-wrapper {
  transform: translate3d(0px, 0, 0);
}
.swiper-container-multirow > .swiper-wrapper {
  flex-wrap: wrap;
}
.swiper-container-multirow-column > .swiper-wrapper {
  flex-wrap: wrap;
  flex-direction: column;
}
.swiper-container-free-mode > .swiper-wrapper {
  transition-timing-function: ease-out;
  margin: 0 auto;
}
.swiper-slide {
  flex-shrink: 0;
  width: 100%;
  height: 100%;
  position: relative;
  transition-property: transform;
}
.swiper-slide-invisible-blank {
  visibility: hidden;
}





.swiper-wrapper {
    transition-timing-function:ease-out;
    transition-duration: 1000ms;
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
