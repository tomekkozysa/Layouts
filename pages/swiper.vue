<template>
  <div class="container">

      <swiper class="swiper">
    <swiper-slide :key="banner" v-for="banner in banners"><img :src="banner"></swiper-slide>
      </swiper>
  
      <!-- <div v-swiper:mySwiper="swiperOption">
        <div class="swiper-wrapper">
        <div class="swiper-slide" :key="banner" v-for="banner in banners">
            <div class="swiper-slide-wrap"><img :src="banner"></div>
        </div>
        </div>
        <div class="swiper-pagination"></div>
        </div> -->


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
            swiperOption: {
            pagination: {
                el: '.swiper-pagination'
            },
            // ...
            }
        }
    },
    methods:{

    },
    mounted(){}

        
        /*
    
    const slider = document.querySelector('.items');
let isDown = false;
let startX;
let scrollLeft;

slider.addEventListener('mousedown', (e) => {
  isDown = true;
  slider.classList.add('active');
  startX = e.pageX - slider.offsetLeft;
  scrollLeft = slider.scrollLeft;
});
slider.addEventListener('mouseleave', () => {
  isDown = false;
  slider.classList.remove('active');
});
slider.addEventListener('mouseup', () => {
  isDown = false;
  slider.classList.remove('active');
});
slider.addEventListener('mousemove', (e) => {
  if(!isDown) return;
  e.preventDefault();
  const x = e.pageX - slider.offsetLeft;
  const walk = (x - startX) * 3; //scroll-fast
  slider.scrollLeft = scrollLeft - walk;
  console.log(walk);
});
    
    */
}
</script>

<style>

/* @import 'https://cdn.jsdelivr.net/npm/swiper@5.3.6/css/swiper.min.css'; */

.container *{
    box-sizing: border-box;
}
.__container {

  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;

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
}

.swiper-slide {
    flex-shrink: 0;
    width: 100%;
    height: 100%;
    position: relative;
    transition-property: transform;
}




.swiper-slide img{
    display: block;
    max-width:100%;
    width:auto;
    max-height:100%;

    /* object-fit: contain; */
}
.swiper{
    margin-top:10vh;
}
.swiper-slide{
    display: flex;
    align-items: center;
    justify-content: center;
    /* border: 2px solid yellow; */
    box-sizing: border-box;
    height:80vh;

}
/* .swiper-slide-wrap{
    display: flex;
    width:100vw;
    height:80vh;
    align-items: center;
    justify-content: center;
    border:1px solid red
} */


.slider img{
    width:100%;
    height:auto;
   opacity: .41;
   display: block;
    object-fit:contain;
}
.slider *{
    box-sizing: border-box;
}
.slider{
    display: flex;
    flex-direction: row;       
    flex-wrap:nowrap;
   
    scroll-snap-type: x mandatory;
    overflow-x:auto;
}
.slide{ 
    width: 100vw;
    height: 90vh;
    flex:1 0 100vh;
    /* padding:1vw; */
    /* margin:0 4vw; */
    scroll-snap-align: start;
    border-right:1px solid red;
    display: flex;
    align-items: center;
    justify-content: center;
}
.slide-content{
    background: pink;
    width:100px;
    height:60vh;
}
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

</style>
