<template>
  <div class="header">
    城市选择
    <router-link to="/">
      <div class="iconfont header-back">&#xe624;</div>
    </router-link>
  </div>
</template>
<script>
export default {
  data () {
    return {
    }
  },
  created () { },
  methods: {}
}
</script>
<style lang="less" scoped>
@import "../../assets/styles/varibles.less";
.header {
  position: relative;
  overflow: hidden;
  height: 0.86rem;
  line-height: 0.86rem;
  text-align: center;
  color: #fff;
  background: @bgColor;
  font-size: 0.32rem;
  .header-back {
    top: 0;
    left: 0;
    position: absolute;
    width: 0.64rem;
    text-align: center;
    font-size: 0.4rem;
    color: #fff;
  }
}
</style>
