<template>
  <div class="header">
    <div class="header-left">
      <div class="iconfont back-icon">&#xe624;</div>
    </div>
    <div class="header-input">
      <span class="iconfont">&#xe632;</span>
      输入城市/景点/游玩/主题</div>
    <router-link to="/city">
      <div class="header-right">
        {{this.city}}
        <span class="iconfont arrow-icon">&#xe64a;</span>
      </div>
    </router-link>
  </div>
</template>
<script>
import { mapState } from 'vuex'
export default {
  data () {
    return {
    }
  },
  created () { },
  methods: {},
  computed: {
    ...mapState(['city'])
  }
}
</script>
<style lang="less" scoped>
@import "../../assets/styles/varibles.less";
.header {
  display: flex;
  height: 0.86rem;
  line-height: 0.86rem;
  background-color: @bgColor;
  color: #fff;
  .header-left {
    width: 0.64rem;
    float: left;
    .back-icon {
      text-align: center;
      font-size: 0.4rem;
    }
  }
  .header-input {
    flex: 1;
    height: 0.64rem;
    margin-left: 0.2rem;
    margin-top: 0.12rem;
    background: #fff;
    border-radius: 0.1rem;
    color: #ccc;
    line-height: 0.64rem;
    padding-left: 0.2rem;
  }
  .header-right {
    box-sizing: border-box;
    min-width: 1.04rem;
    padding: 0.1rem;
    float: right;
    text-align: center;
    color: #fff;
    .arrow-icon {
      font-size: 0.24rem;
      margin-left: -0.04rem;
    }
  }
}
</style>
