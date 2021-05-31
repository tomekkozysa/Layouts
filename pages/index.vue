<template>
    <div class="main">
        
        <Navigation :open="is_nav_open" />
        <div class="container" :class="[!hasMouse ? 'has_mouse' : '']">
            <Header :onGridToggle="onGridToggle" :onNavToggle="onNavToggle" />
            <div>
                
                <Swip :collection="bannershd" :goto="displaySlide" />
                
            </div>
            <section :class="gridCSS">
                    <Grid  :collection="bannershd" :onGridSelected="onGridSelected"/>
                </section>
        </div>
    </div>
</template>

<script>

import  Grid from '~/components/Grid.vue'
import  Swip from '~/components/Swip.vue'
import  Header from '~/components/Header.vue'
import  Navigation from '~/components/Navigation.vue'


export default {
    components: {
    Swip,
    Grid,
    Header,
    Navigation
  },
    data(){
        return{
            hasMouse:false,
            mouseTested:false,
            runswiper:null,
            showGrid:false,
            swiper:null,
            is_nav_open:false,
            displaySlide:1,
            
            bannershd: [ 
                '/imghd/rmc_0022.jpg',
                 '/imghd/rmc_0030.jpg',
                // '/imghd/rmc_001.jpg', 
               
                '/imghd/rmc_003.jpg', 
                '/imghd/rmc_004.jpg', 
                '/imghd/rmc_005.jpg', 
                '/imghd/rmc_006.jpg', 
                '/imghd/rmc_007.jpg', 
                // '/imghd/rmc_002.jpg', 
                '/imghd/rmc_008.jpg', 
                // '/imghd/rmc_009.jpg', 
                '/imghd/rmc_0010.jpg', 
                '/imghd/rmc_0011.jpg', 
                '/imghd/rmc_0012.jpg', 
                '/imghd/rmc_0013.jpg', 
                '/imghd/rmc_0014.jpg', 
                '/imghd/rmc_0015.jpg', 
                '/imghd/rmc_0016.jpg', 
                '/imghd/rmc_0017.jpg',
                '/imghd/rmc_0018.jpg',
                // '/imghd/rmc_0019.jpg',
                '/imghd/rmc_0020.jpg',
                '/imghd/rmc_0021.jpg',
                
                '/imghd/rmc_0023.jpg',
                '/imghd/rmc_0024.jpg',
                '/imghd/rmc_0025.jpg',
                '/imghd/rmc_0026.jpg',
                '/imghd/rmc_0027.jpg',
                '/imghd/rmc_0028.jpg',
                '/imghd/rmc_0029.jpg',
               
                '/imghd/rmc_0031.jpg',
                '/imghd/rmc_0032.jpg',
                '/imghd/rmc_0033.jpg',
                '/imghd/rmc_0034.jpg',
                '/imghd/rmc_0035.jpg',
                '/imghd/rmc_0036.jpg',
                '/imghd/rmc_0037.jpg',
                '/imghd/rmc_0038.jpg',
                '/imghd/rmc_0039.jpg',
                '/imghd/rmc_0040.jpg',
                '/imghd/rmc_0041.jpg',
                '/imghd/rmc_0042.jpg',
                '/imghd/rmc_0043.jpg',
                '/imghd/rmc_0044.jpg',
                '/imghd/rmc_0045.jpg',
                '/imghd/rmc_0046.jpg',
                '/imghd/rmc_0047.jpg',
                '/imghd/rmc_0048.jpg',
                 '/imghd/rmc_002.jpg', 
                
            ]
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
        // mouse:function(e){
        //     this.hasMouse = true;
        //     window.removeEventListener('mousemove',this.mouse);
        // },
        onGridSelected:function(index){
            console.log('onGrid selected',index)
            this.displaySlide = index;
            // window.scrollTo({ top: 0, behavior: 'smooth' });
            window.scrollTo({top:0});
            this.showGrid=false;     
        },
        onGridToggle:function(){
            this.showGrid = !this.showGrid;
            if(this.is_nav_open){
                this.is_nav_open = false;
            }
        },
        onNavToggle:function(){
            this.is_nav_open = !this.is_nav_open;
            console.log(this.is_nav_open)
        },
        // onMouseSwiper:function(swp){
        //     console.log('XXXX',swp);
        //     this.runswiper = swp;
        //     swp.slideTo(10);
        // }
    },
    mounted(){

        // if (matchMedia('(hover:hover)').matches) {
        //     this.hasMouse = true;
        // }
        // else{
        //     this.hasMouse = false;
        // }
        //     this.mouseTested = true;

        // console.log(this.hasMouse,this.mouseTested)
        // console.log(this.customSwiperInstanceName);

    }

        
}
</script>

<style>

:root{
    --header-height:80px;
    --nav-height:80vh;
}
html{
    height:100%;
}
._main{
    width: 100%;
    height:100vh;
    overflow: hidden;
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
    font-size: 16px;
    /* color: #35495e; */
    /* letter-spacing: 1px; */
    height:100%;
}

.grid_default{
     padding-top:20vh;
    background: white;
    overflow: hidden;
    position: absolute;
    top:0;left:0;
    transform: translateY(100vh); 
     width:100%;
    z-index:100;
    transition:transform .3s;
    /* height:0; */
    
}

.is_visible{
   z-index:500;
   /* height:100vh; */
   transform: translateY(0vh);
   /* overflow-y:scroll; */
}

.container{
    position:relative;
}
.container.has_mouse{}

</style>
