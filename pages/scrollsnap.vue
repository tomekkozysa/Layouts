<template>
  <div class="container">
    <div class="slider">

        <div class="slide">
            <div class="slide-content"></div>
        </div>
        <div class="slide">
            <div class="slide-content"></div>
        </div>
        <div class="slide">
            <div class="slide-content"></div>
        </div>
        <div class="slide">
            <div class="slide-content"></div>
        </div>
        <div class="slide">
            <div class="slide-content"></div>
        </div>
        <div class="slide">
            <div class="slide-content"></div>
        </div>
       
    </div>
  </div>
</template>

<script>
export default {
    data(){
        return{}
    },
    methods:{

    },
    mounted(){},
    
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
.container {

  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;

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
