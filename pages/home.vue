<template>
  <div class="container" :class="[!hasMouse ? 'has_mouse' : '']">
      <span class="no" @click="toggleGrid">toggle Grid</span>

        <!-- <div :class="[hasMouse ? 'has_mouse' : '', 'swiper-prev']">
            <svg width="24" height="24" xmlns="http://www.w3.org/2000/svg" fill-rule="evenodd" clip-rule="evenodd"><path d="M2.117 12l7.527 6.235-.644.765-9-7.521 9-7.479.645.764-7.529 6.236h21.884v1h-21.883z"/></svg>
        </div>
        <div :class="[hasMouse ? 'has_mouse' : '', 'swiper-next']">
            <svg width="24" height="24" xmlns="http://www.w3.org/2000/svg" fill-rule="evenodd" clip-rule="evenodd"><path d="M21.883 12l-7.527 6.235.644.765 9-7.521-9-7.479-.645.764 7.529 6.236h-21.884v1h21.883z"/></svg>
        </div> -->
        <swiper 
        @inInit="onMouseSwiper"
        v-if="mouseTested && hasMouse" class="swiper" :options="swiperMouseOptions" >
            <swiper-slide :key="banner" v-for="banner in banners"><img :src="banner"></swiper-slide>
        </swiper>

        <swiper v-if="mouseTested && !hasMouse" class="swiper" :options="swiperTouchOptions" >
            <swiper-slide :key="banner" v-for="banner in banners"><img :src="banner"></swiper-slide>
        </swiper>    
      
      <section :class="gridCSS">
          <Grid  :collection="banners" :onGridSelected="onGridSelected"/>
        </section>
    </div>
</template>

<script>
import { Swiper, SwiperSlide, directive } from 'vue-awesome-swiper'
import  Grid from '~/components/Grid.vue'
export default {
    components: {
    Swiper,
    SwiperSlide,
    Grid
  },
  
    data(){
        return{
            hasMouse:false,
            mouseTested:false,
            runswiper:null,
            showGrid:false,
            banners: [ 
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
    classObject: function () {
        return {
        show_nav: this.hasMouse,
    
        }
    },
    gridCSS: function () {
        return {
            is_visible: this.showGrid,
            grid_default:true
    
        }
    }
    },

    methods:{
        mouse:function(e){
            this.hasMouse = true;
            window.removeEventListener('mousemove',this.mouse);
        },
        onGridSelected:function(index){
            this.displaySlide = index;
            window.scrollTo({ top: 0, behavior: 'smooth' });
            this.showGrid=false;     
            // console.log(this.$refs.swiperMouse)        
            // this.$refs.swiperMouse.slideTo(index)
        },
        toggleGrid:function(){
            this.showGrid = !this.showGrid;
        },
        onMouseSwiper:function(swp){
            console.log('XXXX',swp);
            this.runswiper = swp;
            swp.slideTo(10);
        }
    },
    mounted(){

        if (matchMedia('(hover:hover)').matches) {
            this.hasMouse = true;
        }
        else{
        this.hasMouse = false;
        }
        this.mouseTested = true;

        console.log(this.hasMouse,this.mouseTested)
        //window.addEventListener('mousemove',this.mouse);


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

.grid_default{
    background: white;
}
.is_visible{
    position: absolute;
    top:0;left:0;
    width:100vw;
    z-index:100;

    /* transform: translateY(100vh); */
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
    width:20%;
    height:70vh;
    /* background: pink; */
    cursor: pointer;
    position:absolute;
    top:15vh;
    left:0;
    z-index:1000;
    display: flex;
    align-items: center;
    padding:40px;
    pointer-events: none;
    opacity:0;
}
.swiper-next{
    right:0;
    left:auto;    
    justify-content: flex-end;
}
.swiper-prev{    
    justify-content: flex-start;
}

.swiper-next:focus,
.swiper-prev:focus{
    outline:0
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


.swiper-next.has_mouse,
.swiper-prev.has_mouse{
    pointer-events:initial;
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
    max-height:80%;
    /* height:80%; */
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
