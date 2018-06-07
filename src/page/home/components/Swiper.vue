<template>
  <div class="wrapper">
    <swiper :options="swiperOption">
      <!-- slides -->
      <swiper-slide>
        <img src="http://img1.qunarzz.com/piao/fusion/1709/39/b98fdb3ee7478e02.jpg_750x200_be64b756.jpg">
      </swiper-slide>
      <swiper-slide>
        <img src="http://img1.qunarzz.com/piao/fusion/1803/98/0a2e0bd8eb0c0802.png_750x200_0a34d4a8.png">
      </swiper-slide>
      <swiper-slide>
        <img src="http://img1.qunarzz.com/piao/fusion/1805/3b/ef86879aa50e3002.jpg_750x200_2a108508.jpg">
      </swiper-slide>
      <div class="swiper-pagination" slot="pagination"></div>
    </swiper>
  </div>
</template>
<script>
  export default{
    name: 'HomeSwiper',
    data(){
      return {
        swiperOption: {
          loop: true,
          autoplay: 3000
        }
      }
    },
  }
</script>
<style scoped>
  .wrapper{
    width: 100%;
    height: 0;
    padding-bottom: 26.7%;
  }
  .swiper-slide>img{
    width: 100%;
  }
</style>
