<template>
  <div>
    <home-header></home-header>
    <home-swiper></home-swiper>
    test
  </div>
</template>
<script>
  import HomeHeader from './home/components/Header'
  import HomeSwiper from './home/components/Swiper'
  export default{
    name: 'Home',
    components: {
      HomeHeader,
      HomeSwiper
    },
    data () {
      return {}
    },
    mounted(){
      this.axios.get('api/index.json')
        .then(res => {
          console.log(res)
        })
    }
  }
</script>
<style scoped lang="less" type="text/less">

</style>
