<template>
  <div class="wrapper">
    <swiper :options="swiperOption">
    <swiper-slide v-for="item in swiperList" :key="item.id">
      <img class="swiper-img" :src="item.imgUrl" />
    </swiper-slide>
    <div class="swiper-pagination"  slot="pagination"></div>
  </swiper>
  </div>
</template>
<script>
export default {
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination'
      },
      swiperList: [{
        id: '0001',
        imgUrl: require('../assets/images/1.jpg')
      },{
        id: '0002',
        imgUrl: require('../assets/images/2.jpg')
      }]
    }
  },
  created () {},
  methods: {}
}
</script>
<style lang="less" scoped>
.wrapper /deep/ .swiper-pagination-bullet-active {
  background: #fff !important;
}
.wrapper {
  overflow: hidden;
  width: 100%;
  height: 0;
  padding-bottom: 26.66%;
  background: #eee;
  .swiper-img{
    width: 100%;
  }
}
</style>