<template>
  <div class="search">
    <input type="text"
           placeholder="输入城市名或拼音"
           class="search-input">
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
.search {
  padding: 0 0.1rem;
  height: 0.72rem;
  background: @bgColor;
  .search-input {
    box-sizing: border-box;
    height: 0.62rem;
    line-height: 0.62rem;
    width: 100%;
    padding: 0 0.1rem;
    text-align: center;
    border-radius: 0.06rem;
    color: #666;
  }
}
</style>
