<template>
  <div class="">
    <div class="recommend-title">周末去哪儿</div>
    <ul>
      <li class="item border-bottom"
          v-for="item of recommendList"
          :key="item.id">
        <div class="item-img-wrapper">
          <img :src="item.imgUrl"
               class="item-img">
        </div>
        <div class="item-info">
          <p class="item-title">{{item.title}}</p>
          <p class="item-desc">{{item.desc}}</p>
        </div>
      </li>
    </ul>
  </div>
</template>
<script>
export default {
  data () {
    return {
      recommendList: [{
        id: '0001',
        imgUrl: require('../assets/images/weekend_1.jpg'),
        title: '长沙世界之窗',
        desc: '长沙世界之窗位于湖南省长沙市东北郊区浏阳河畔，是由湖南电广传媒股份有限公司、深圳华侨城控股股份有限公司和香港中旅集团共同投资兴建的文化主题公园。'
      }, {
        id: '0002',
        imgUrl: require('../assets/images/weekend_2.jpg'),
        title: '宁乡炭河古城',
        desc: '宋城炭河古城：因炭河里遗址而来，位于湖南省长沙市宁乡市，为中国首个周文化主题公园。'
      }, {
        id: '0003',
        imgUrl: require('../assets/images/weekend_3.jpg'),
        title: '湖南省博物馆',
        desc: '湖南省博物馆位于湖南省长沙市开福区东风路50号。是湖南省最大的历史艺术类博物馆，占地面积4.9万平方米，总建筑面积为9.1万平方米，是首批国家一级博物馆。'
      }, {
        id: '0004',
        imgUrl: require('../assets/images/weekend_4.jpg'),
        title: '长沙方特东方神画',
        desc: '隶属于深圳华强集团有限公司的美丽中国 · 长沙文化产业示范园长沙方特东方神画于2015年11月动工建设，将在2019年建成开园，预计年设计接待游客300万人次。'
      }, {
        id: '0005',
        imgUrl: require('../assets/images/weekend_5.jpg'),
        title: '长沙乐水魔方水世界',
        desc: '乐水魔方水世界,是长沙纯天然全景园林生态水世界。园区总占地面积超10万平方米,拥有近两万平米海啸造浪池、28米高极限穿梭等多个大型水上娱乐设备。'
      }]
    }
  },
  created () { },
  methods: {}
}
</script>
<style lang="less" scoped>
@import "../assets/styles/mixins.less";
.recommend-title {
  line-height: 0.8rem;
  background: #eee;
  margin-top: 0.2rem;
  text-indent: 0.2rem;
}
.item {
  .item-img-wrapper {
    height: 0;
    overflow: hidden;
    padding-bottom: 33.9%;
    .item-img {
      width: 100%;
    }
  }
  .item-info {
    padding: 0.1rem;
    .item-title {
      line-height: 0.54rem;
      font-size: 0.32rem;
      .ellipsis();
    }
    .item-desc {
      line-height: 0.4rem;
      color: #ccc;
      .ellipsis();
    }
  }
}
</style>
