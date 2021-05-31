<template>
    <div class="grid">
        <img :src="banner"  :key="banner" v-for="(banner,index) in collection" @click="toggle($event,index)" />
    </div>
</template>
<script>
export default {
    components: {},
    directives: {},
    props:{
        collection:Array,
        onGridSelected:Function,
    },
    data(){
        return{
            hasMouse:false,
            mouseTested:false,
            _banners: [ 
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
        }  
    },
    computed: {
    },
    methods:{
        /*@click="toggle($event,index)"*/
        toggle:function(ev, index){
            // window.scrollTo({ top: 0, behavior: 'smooth' });
            console.log('grid clicked: ', index);
            this.onGridSelected(index);
        }
    }
}
</script>
<style scoped>

.grid{
    --column-count:3;
    --cell-w:250px;
    --img-p:20px;
    display: grid;
    grid-template-columns: repeat(var(--column-count), var(--cell-w));
    grid-auto-rows:var(--cell-w);
    margin: 0 auto;
   width: calc( var(--column-count) * var(--cell-w));
}


@media (min-width: 1024px) { 
    .grid{--column-count:4;}
}
@media (min-width: 1280px) { 
    .grid{--column-count:5;}
}

@media (max-width: 768px) { 
    .grid{--column-count:2;}
}
@media (max-width: 640px) { 
    .grid{--column-count:2;}
}
@media (max-width: 480px) { 
    .grid{
        --column-count:2;
        --cell-w:180px;
         --img-p:10px;
     }
   
}

.grid,
.grid * {
    box-sizing: border-box;
}
img{
    width: var(--cell-w);
    height: var(--cell-w);
    width: 100%; height:100%;
    display:block;
    object-fit: cover;
    padding:var(--img-p);
    box-sizing: border-box;
    cursor: pointer;
}
</style>
