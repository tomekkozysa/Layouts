<template>
  <div class="swiper-container">
      <!-- Additional required wrapper -->
      <div class="swiper-wrapper">
          <!-- Slides -->
          <div class="swiper-slide" :key="image" v-for="image in collection">
               <img :src="image">
          </div>
        </div>

        <div :class="[hasMouse ? 'has_mouse' : '', 'swiper-prev']">
            <svg width="24" height="24" xmlns="http://www.w3.org/2000/svg" fill-rule="evenodd" clip-rule="evenodd"><path d="M2.117 12l7.527 6.235-.644.765-9-7.521 9-7.479.645.764-7.529 6.236h21.884v1h-21.883z"/></svg>
        </div>
        <div :class="[hasMouse ? 'has_mouse' : '', 'swiper-next']">
            <svg width="24" height="24" xmlns="http://www.w3.org/2000/svg" fill-rule="evenodd" clip-rule="evenodd"><path d="M21.883 12l-7.527 6.235.644.765 9-7.521-9-7.479-.645.764 7.529 6.236h-21.884v1h21.883z"/></svg>
        </div>

  </div>
</template>

<script>
import Swiper, { Navigation, Keyboard, Mousewheel } from 'swiper'

Swiper.use([ Navigation, Keyboard, Mousewheel ])

export default {
    name:'swip',
    data(){
        return{
            slides:null,
            swiperMouseOptions: {
                // loadPrevNext:false,                      
                loop: true,
                loopedSlides:45,
                freeMode: false,
                slidesPerView:1,
                // freeModeSticky: true,
                // centeredSlides: true,
                spaceBetween: 30,
                grabCursor: true,           
                mousewheel: true,
                speed:666,
                cssMode:false,
                keyboard: {
                    enabled: true,
                    onlyInViewport: false,
                },
                navigation: {
                    nextEl: '.swiper-next',
                    prevEl: '.swiper-prev',
                },
                
            },
            swiperTouchOptions: {
                // loadPrevNext:true,                      
                loop: true,
                loopedSlides:45,
                freeMode: true,
                slidesPerView:1,
                freeModeSticky: true,
                centeredSlides: true,
                spaceBetween: 30,
                grabCursor: true,           
                mousewheel: true,
                speed:200,
                cssMode:true,
                
            },
            hasMouse:false,
            mouseTested:false
            
        }
    },
    props:{
        collection:Array,
        goto:Number,
        onSwiperUpdate:Function,
    },
    watch:{
        goto:function(n,o){
            console.log('goto watcher:',n)
            if(n===o || n === this.slides.activeIndex){
                console.log('n===o',n===o)
                return;
            }
            console.log('goto', n,o, this.collection[n], n)
            console.log('slide from', this.slides.activeIndex)
            // this.slides.params.speed = 60;
            this.$nextTick(()=>{
            // this.slides.slideTo(n,0);
            // this.slides.slideToLoop(n-1,0)
            this.slides.slideToLoop(n,0)
            this.slides.slideReset(0);
            // this.slides.params.speed = 666;
            console.log('slide in', this.slides.activeIndex)
            })
            
        }
    },
    mounted() {        
        if (matchMedia('(hover:hover)').matches) {
            this.hasMouse = true;
        }
        else{
            this.hasMouse = false;
        }        
        this.mouseTested = true;
        let options = this.hasMouse ? this.swiperMouseOptions : this.swiperTouchOptions;
        let s = new Swiper('.swiper-container', options )
        this.slides = s;

        this.slides.on('slideChange',  (e) => {
                console.log('slide changed',e, e.activeIndex);
                this.onSwiperUpdate(e.activeIndex);
            });
    }
}
</script>

<style scoped>


.swiper-container {
    /* desktop */
    --swip-height:calc(100vh - calc(2 * var(--header-height)))
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
    height:var(--swip-height);
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
    display: flex;
    align-items: center;
    justify-content: center;
    box-sizing: border-box;
    height:100%;
    -webkit-transform: translate3d(0, 0, 0);
}


.swiper-slide img{
    display: block;
    max-width:90%;
    width:auto;
    max-height:100%;
    /* height:80%; */
}


.swiper-next,
.swiper-prev{
    width:20%;
    height:var( --nav-height);
    /* background: pink; */
    cursor: pointer;
    position:absolute;
    top:0;
    left:0;
    z-index:1000;
    display: flex;
    align-items: center;
    pointer-events: none;
    opacity:0;
}
.swiper-next{
    right:0;
    left:auto;    
    justify-content: flex-end;
    padding-right:20px;
}
.swiper-prev{    
    justify-content: flex-start;
    padding-left:20px;
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





</style>
