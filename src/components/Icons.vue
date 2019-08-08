<template>
  <div class="icons">
    <swiper :options="swiperOption">
      <swiper-slide v-for="(page,index) in pages"
                    :key="index">
        <div class="icon"
             v-for="item in page"
             :key="item.id">
          <div class="icon-img">
            <img class="icon-img-content"
                 :src="item.imgUrl">
          </div>
          <p class="icon-desc">{{item.desc}}</p>
        </div>
      </swiper-slide>
      <div class="swiper-pagination"
           slot="pagination"></div>
    </swiper>
  </div>
</template>
<script>
export default {
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        autoplay: false
      },
      iconList: [{
        id: '0001',
        imgUrl: require('../assets/upload/1.png'),
        desc: '景点门票'
      }, {
        id: '0002',
        imgUrl: require('../assets/upload/2.png'),
        desc: '天门山公园'
      }, {
        id: '0003',
        imgUrl: require('../assets/upload/3.png'),
        desc: '长沙必游'
      }, {
        id: '0004',
        imgUrl: require('../assets/upload/4.png'),
        desc: '夏日漂流'
      }, {
        id: '0005',
        imgUrl: require('../assets/upload/5.png'),
        desc: '一日游'
      }, {
        id: '0006',
        imgUrl: require('../assets/upload/6.png'),
        desc: '动植物园'
      }, {
        id: '0007',
        imgUrl: require('../assets/upload/7.png'),
        desc: '自然风光'
      }, {
        id: '0008',
        imgUrl: require('../assets/upload/8.png'),
        desc: '湘西凤凰'
      }, {
        id: '0009',
        imgUrl: require('../assets/upload/8.png'),
        desc: '湘西凤凰'
      }]
    }
  },
  created () { },
  methods: {},
  computed: {
    pages () {
      const pages = []
      this.iconList.forEach((item, index) => {
        const page = Math.floor(index / 8)
        if (!pages[page]) {
          pages[page] = []
        }
        pages[page].push(item)
      })
      return pages
    }
  }
}
</script>
<style lang="less" scoped>
@import "../assets/styles/varibles.less";
@import "../assets/styles/mixins.less";
.icons /deep/ .swiper-container {
  height: 0;
  padding-bottom: 50%;
}
.icons {
  overflow: hidden;
  height: 0;
  padding-bottom: 50%;
  margin-top: 0.1rem;
  .icon {
    position: relative;
    overflow: hidden;
    float: left;
    width: 25%;
    height: 0;
    padding-bottom: 25%;
    .icon-img {
      position: absolute;
      top: 0;
      left: 0;
      right: 0;
      bottom: 0.44rem;
      box-sizing: border-box;
      padding: 0.1rem;
      .icon-img-content {
        display: block;
        height: 100%;
        margin: 0 auto;
      }
    }
    .icon-desc {
      position: absolute;
      left: 0;
      right: 0;
      bottom: 0;
      height: 0.44rem;
      text-align: center;
      color: @darkTextColor;
      .ellipsis();
    }
  }
}
</style>
