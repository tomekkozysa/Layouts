<template>
    <div :class="classObject" class="navigation-wrapper">
        <div :class="classObject" class="navigation">
            <p><a class="navigation-link" href="mailto:ron.f.mcelroy@gmail.com">ron.f.mcelroy@gmail.com</a></p>
            <p><a class="navigation-link" href="te:+44-7813-89-94-43">+44 (0)7813 89 94 43</a></p>
        </div>      
  </div>
</template>

<script>


export default {
    components: {},
    directives: {},
    props:{
        open:Boolean
    },
    data(){
        return{
            
            
        }
        
           
    },
    computed:{
        classObject: function () {
        return {
            is_open: this.open,            
        }
        
    },
    },
    methods:{
        /*@click="toggle($event,index)"*/
       

    }
        
}
</script>

<style scoped>
.navigation-wrapper{
    --nav-width:400px;
    --nav-shift:-400px;

    width: 100%;
    height:100vh;
    position: fixed;
    top:0;
    left:0;
    background:rgba(255,255,255,0);
    transition: background .15s ease-in-out;
    

}
.navigation-wrapper.is_open{
z-index:5000;
background:rgba(255,255,255,.6);
transition: background .5s ease-in-out
}
.navigation{
    max-width:var(--nav-width);
    width:100%;
    background:rgba(226, 232, 238,1);
    height:100vh;
    transform: translateX(0);
    position: absolute;
    top:0;
    right: var(--nav-shift);
    z-index:1000;
   text-align: center;
   padding-top:120px;
   transition:transform .13s ease-in-out;

}
.navigation.is_open{
    transform: translateX(var(--nav-shift));
    transition:transform .3s ease-in-out;
}
p{
    margin-top:20px;
}

.navigation-link{
    text-decoration: none;
    font-weight: 400;
    color:#444;
}
</style>
