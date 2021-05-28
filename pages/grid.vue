<template>
  <div class="container" :class="[!hasMouse ? 'has_mouse' : '']">
  
         <div class="grid">
                <div class="cell" :key="banner" v-for="(banner,index) in banners">
                    <img :src="banner"  />
                    <span class="no">{{index}}</span>
                </div>
        </div>

      
  </div>
</template>

<script>
import { Swiper, SwiperSlide, directive } from 'vue-awesome-swiper'

export default {
    components: {
   
  },
  directives: {
   },
    data(){
        return{
            hasMouse:false,
            mouseTested:false,
            banners: [ 
                '/img/rmc_002.jpg', 
                '/img/rmc_003.jpg', 
                '/img/rmc_004.jpg', 
                '/img/rmc_005.jpg', 
                '/img/rmc_006.jpg', 
                '/img/rmc_007.jpg', 
                '/img/rmc_002.jpg', 
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
                '/img/rmc_0018.jpg',
                '/img/rmc_0019.jpg',
                '/img/rmc_0020.jpg',
                '/img/rmc_0021.jpg',
                '/img/rmc_0022.jpg',
                '/img/rmc_0023.jpg',
                '/img/rmc_0024.jpg',
                '/img/rmc_0025.jpg',
                '/img/rmc_0026.jpg',
                '/img/rmc_0027.jpg',
                '/img/rmc_0028.jpg',
                '/img/rmc_0029.jpg',
                '/img/rmc_0030.jpg',
                '/img/rmc_0031.jpg',
                '/img/rmc_0032.jpg',
            ],
            swiperMouseOptions: {
                loadPrevNext:true,                      
                loop: true,
                freeMode: false,
                freeModeSticky: true,
                centeredSlides: true,
                spaceBetween: 30,
                grabCursor: true,           
                mousewheel: true,
                speed:750,
                cssMode:false,
                keyboard: {
                    enabled: true,
                    onlyInViewport: false,
                },
                navigation: {
                    nextEl: '.swiper-next',
                    prevEl: '.swiper-prev',
                },
                // pagination: {
                //     el: '.swiper-pagination',
                //     type: 'bullets',
                //     dynamicBullets:true,
                // }
            },
            swiperTouchOptions: {
                loadPrevNext:true,                      
                loop: true,
                freeMode: true,
                freeModeSticky: true,
                centeredSlides: true,
                spaceBetween: 30,
                grabCursor: true,           
                mousewheel: true,
                speed:200,
                cssMode:true,
                
            }
        }
        
           
    },
    computed: {
    },
    methods:{
        /*@click="toggle($event,index)"*/
        toggle:function(ev, index){
            window.scrollTo({ top: 0, behavior: 'smooth' });
            console.log(index)
        }

    }
        
}
</script>

<style>


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
  font-size: 16px;
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
.container.has_mouse{

}
.grid{
    transform:translateY(0vh);
    display:flex;
    flex-direction: row;
    flex-wrap: wrap;
    justify-content: flex-start;
    align-content: stretch;
    padding: 0;
    max-width: 1200px;
    margin: 0 auto;
    /* margin-top:80vh; */

    /* transition: transform .2s; */
}

.container:hover .grid{
    transform:translateY(0);
}
.cell{
   flex: 0 0 auto;
    /*flex-grow: 1;*/
    position:relative;
}
img{
    /* flex:1 1 400px; */
    width: 300px;
    height: 300px;
    display:block;
    flex: 0 0 auto;
    object-fit: cover;
    padding:20px;
}
img:hover{
    
}
.no{
    position:absolute;
    top:40px;left:40px;
    background: wheat;
    display: inline-block;
    padding:20;
}
</style>
