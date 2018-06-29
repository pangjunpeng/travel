<template>
  <div>
    <home-header @popup="alertPopup"></home-header>
    <home-swiper></home-swiper>
    <span @click="popupShow=true">actionsheet显示</span>
    <span @click="selectShow=true">select显示</span>
    <h1>{{sRes.text}}</h1>
    <popup :opts="popupData" :isShow.sync="popupShow"></popup>
    <my-select :lists="lists" :isShow.sync="selectShow" @result="getRes"></my-select>
  </div>
</template>
<script>
  import HomeHeader from './home/components/Header'
  import HomeSwiper from './home/components/Swiper'
  import Popup from './home/components/Popup'
  import mySelect from './home/components/Select'
  export default{
    name: 'Home',
    components: {
      HomeHeader,
      HomeSwiper,
      Popup,
      mySelect
    },
    data () {
      return {
        popupData: [{
          text      : '行内转账',
          cssClasses: 'content',
          handler   : function () {
            alert('行内转账')
          }
        }, {
          text      : '跨行转账',
          cssClasses: 'content',
          handler   : function () {
            alert('跨行转账')
          }
        }],
        lists: [
          {id: 0, value: "item0", text: "选项1"},
          {id: 1, value: "item1", text: "选项2"},
          {id: 2, value: "item2", text: "选项3"},
          {id: 3, value: "item3", text: "选项4"},
          {id: 4, value: "item4", text: "选项5"},
          {id: 5, value: "item5", text: "选项6"},
          {id: 6, value: "item6", text: "选项7"},
          {id: 7, value: "item7", text: "选项8"},
          {id: 8, value: "item8", text: "选项9"},
          {id: 9, value: "item9", text: "选项10"}],
        popupShow: false,
        selectShow: false,
        sRes: {}
      }
    },
    methods: {
      alertPopup(data){
        this.popupData = data
      },
      getRes(data){
        this.sRes = data
      }
    },
    mounted(){
      this.axios.get('api/index.json')
        .then(res => {
          console.log(res)
        })
    }
  }
</script>
<style lang="less" type="text/less">
  .content{
    color: #000;
  }
</style>
