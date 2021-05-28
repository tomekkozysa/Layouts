<template>
    
        <div class="grid">
            <img :src="banner"  key="banner" v-for="(banner,index) in collection" @click="toggle($event,index)" />
            <!-- <div class="cell" : >
                
                
            </div> -->
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
            console.log(index);
            this.onGridSelected(index)
        }

    }
        
}
</script>

<style scoped>

/* 
.container{
    position:relative;
}
.container.has_mouse{

} */
.grid{
    --column-count:4;
    --cell-w:250px;
   
    display: grid;
    /* transform:translateY(0vh); */
    grid-template-columns: repeat(var(--column-count), var(--cell-w));
    /* grid-template-rows: repeat(4, var(--cell-w)); */
    grid-auto-rows:var(--cell-w);
    margin: 0 auto;
    margin-top:20vh;
    width: calc( var(--column-count) * var(--cell-w));

    /* transition: transform .2s; */
}
.grid,
.grid * {
    box-sizing: border-box;
}
.container:hover .grid{
    transform:translateY(0);
}
.cell{
   /* width: var(--cell-w); */
   /* height: ; */
}
img{
    /* flex:1 1 400px; */
    width: var(--cell-w);
    height: var(--cell-w);
    width: 100%; height:100%;
    display:block;
    /* flex: 0 0 auto; */
    object-fit: cover;
    padding:20px;
    box-sizing: border-box;
    cursor: pointer;
    
    
}
img:hover{
     
}
.no{
    position:absolute;
    top:20px;left:20px;
    background: wheat;
    display: inline-block;
    padding:10px;
}
</style>
