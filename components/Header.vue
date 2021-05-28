<template>
  <div class="header">
         <img class="logo" src="/rmcnm.png" />
         <div class="header-nav">
             <img class="header-nav-icon" src="/iconmonstr-view-5.svg" alt="" @click="onGridToggle">
             <img class="header-nav-icon" src="/iconmonstr-email-14.svg" alt="" @click="onNavToggle"> 
              
         </div>
      
  </div>
</template>

<script>


export default {
    components: {},
    directives: {},
    props:{
        collection:Array,
        onGridToggle:Function,
        onNavToggle:Function,
    },
    data(){
        return{
            
            
        }
        
           
    },
    computed: {
    },
    methods:{
        /*@click="toggle($event,index)"*/
       

    }
        
}
</script>

<style scoped>
.header{
    padding:0 24px;
    height:80px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    position: relative;
    z-index:5000;
}
.logo{
    width:200px;
    /* image-rendering: crisp-edges; */
    justify-self: flex-start;
}
.header-nav{
    justify-self: flex-end;
}
.header-nav-icon{
    opacity:.55;
    margin:0 10px;
    cursor: pointer;
}
</style>
