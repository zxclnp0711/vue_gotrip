<template>
  <div class="home">
    <home-header></home-header>
    <home-swiper :list="swiperList"></home-swiper>
    <home-icons :list="iconList"></home-icons>
    <home-recommend :list="recommendList"></home-recommend>
    <home-weekend :list="weekendList"></home-weekend>
  </div>
</template>
<script>
import HomeHeader from '../components/home/Header'
import HomeSwiper from '../components/home/Swiper'
import HomeIcons from '../components/home/Icons'
import HomeRecommend from '../components/home/Recommend'
import HomeWeekend from '../components/home/Weekend'
import { mapState } from 'vuex'
export default {
  data () {
    return {
      swiperList: [],
      iconList: [],
      weekendList: [],
      recommendList: [],
      lastCity: ''
    }
  },
  created () { },
  methods: {
    getHomeInfo () {
      this.$axios.get('/api/index.json?city=' + this.city)
        .then(this.getHomeInfoSucc)
    },
    getHomeInfoSucc (res) {
      res = res.data
      if (res.ret && res.data) {
        const data = res.data
        this.swiperList = data.swiperList
        this.iconList = data.iconList
        this.weekendList = data.weekendList
        this.recommendList = data.recommendList
      }
    }
  },
  components: {
    HomeHeader,
    HomeSwiper,
    HomeIcons,
    HomeRecommend,
    HomeWeekend
  },
  mounted () {
    this.lastCity = this.city
    this.getHomeInfo()
  },
  computed: {
    ...mapState(['city'])
  },
  activated () {
    if (this.lastCity !== this.city) {
      this.lastCity = this.city
      this.getHomeInfo()
    }
  }
}
</script>
<style lang="less" scoped>
</style>
