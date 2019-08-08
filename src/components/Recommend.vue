<template>
  <div class="">
    <div class="recommend-title">热销推荐</div>
    <ul>
      <li class="item border-bottom"
          v-for="item of recommendList"
          :key="item.id">
        <img :src="item.imgUrl"
             class="item-img">
        <div class="item-info">
          <p class="item-title">{{item.title}}</p>
          <p class="item-desc">{{item.desc}}</p>
          <button class="item-button">查看详情</button>
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
        imgUrl: require('../assets/images/hot_1.jpg'),
        title: '长沙世界之窗',
        desc: '长沙世界之窗位于湖南省长沙市东北郊区浏阳河畔，是由湖南电广传媒股份有限公司、深圳华侨城控股股份有限公司和香港中旅集团共同投资兴建的文化主题公园。'
      }, {
        id: '0002',
        imgUrl: require('../assets/images/hot_2.jpg'),
        title: '宁乡炭河古城',
        desc: '宋城炭河古城：因炭河里遗址而来，位于湖南省长沙市宁乡市，为中国首个周文化主题公园。'
      }, {
        id: '0003',
        imgUrl: require('../assets/images/hot_3.jpg'),
        title: '湖南省博物馆',
        desc: '湖南省博物馆位于湖南省长沙市开福区东风路50号。是湖南省最大的历史艺术类博物馆，占地面积4.9万平方米，总建筑面积为9.1万平方米，是首批国家一级博物馆。'
      }, {
        id: '0004',
        imgUrl: require('../assets/images/hot_4.jpg'),
        title: '长沙方特东方神画',
        desc: '隶属于深圳华强集团有限公司的美丽中国 · 长沙文化产业示范园长沙方特东方神画于2015年11月动工建设，将在2019年建成开园，预计年设计接待游客300万人次。'
      }, {
        id: '0005',
        imgUrl: require('../assets/images/hot_5.jpg'),
        title: '长沙乐水魔方水世界',
        desc: '乐水魔方水世界,是长沙纯天然全景园林生态水世界。园区总占地面积超10万平方米,拥有近两万平米海啸造浪池、28米高极限穿梭等多个大型水上娱乐设备。'
      }, {
        id: '0006',
        imgUrl: require('../assets/images/hot_6.jpg'),
        title: '长沙生态动物园',
        desc: '长沙生态动物园位于长沙市天心区，前身是位于烈士公园畔的长沙动物园。'
      }, {
        id: '0007',
        imgUrl: require('../assets/images/hot_7.jpg'),
        title: '华谊兄弟（长沙）电影小镇',
        desc: '华谊兄弟（长沙）电影小镇目位于长沙市中心以南、湘江以西，湘江新区大王山旅游度假中心内，规划总用地约1000亩，总建筑面积约15万方，分两期滚动开发，项目总投资超过30亿元。'
      }, {
        id: '0008',
        imgUrl: require('../assets/images/hot_8.png'),
        title: '大围山峡谷漂流',
        desc: '大围山峡谷漂流位于大围山国家森林公园南麓，崇山峻岭深处的大围山峡谷——花门河。'
      }, {
        id: '0009',
        imgUrl: require('../assets/images/hot_9.jpg'),
        title: '长沙乐民水上乐园',
        desc: '长沙市乐民水上乐园和山地机动项目游乐园,坐落在长沙市中心区“湖南省森林植物园”园区内。'
      }, {
        id: '0010',
        imgUrl: require('../assets/images/hot_10.jpg'),
        title: '海立方海洋公园',
        desc: '海立方海世界位于湖南省长沙市雨花区圭塘河滨水公园核心地段，由北京海洋城集团投资2亿元打造。'
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
  display: flex;
  height: 1.9rem;
  overflow: hidden;
  .item-img {
    width: 1.7rem;
    height: 1.7rem;
    padding: 0.1rem;
  }
  .item-info {
    flex: 1;
    padding: 0.1rem;
    min-width: 0;
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
    .item-button {
      line-height: 0.44rem;
      margin-top: 0.16rem;
      background: #ff9300;
      padding: 0 0.2rem;
      border-radius: 0.06rem;
      color: #fff;
    }
  }
}
</style>
