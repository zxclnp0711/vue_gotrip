<template>
  <div class="">
    <div class="recommend-title">周末去哪儿</div>
    <ul>
      <li class="item border-bottom"
          v-for="item of list"
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
    }
  },
  props: {
    list: Array
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
