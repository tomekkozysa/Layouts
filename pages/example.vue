<template>
  <div class="swiper-container">
      <!-- Additional required wrapper -->
      <div class="swiper-wrapper">
          <!-- Slides -->
          <div class="swiper-slide">Slide 1</div>
          <div class="swiper-slide">Slide 2</div>
          <div class="swiper-slide">Slide 3</div>
          ...
      </div>
      <!-- If we need pagination 
      <div class="swiper-pagination"></div>-->

      <!-- If we need navigation buttons 
      <div class="swiper-button-prev"></div>
      <div class="swiper-button-next"></div>-->

      <!-- If we need scrollbar 
      <div class="swiper-scrollbar"></div> -->

  </div>
</template>

<script>
import Swiper, { Navigation, Pagination } from 'swiper'
import 'swiper/swiper-bundle.css'

Swiper.use([ Navigation, Pagination ])

export default {
    data(){
        return{
            slides:null
        }
    },
  mounted() {
    let s = new Swiper('.swiper-container', {
      loop: true,
      pagination: {
        el: '.swiper-pagination',
      },
      navigation: {
        nextEl: '.swiper-button-next',
        prevEl: '.swiper-button-prev',
      },
      scrollbar: {
        el: '.swiper-scrollbar',
      },
    })

    this.slides = s;
  }
}
</script>

<style scoped>
.swiper-container {
  width: 600px;
  height: 300px;
}
</style>
