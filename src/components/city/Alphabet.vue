<template>
  <div>
    <ul class="list">
      <li class="item"
          v-for="(item,key) in cities"
          :key="key">{{key}}</li>
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
    cities: Object
  },
  created () { },
  methods: {}
}
</script>
<style lang="less" scoped>
@import "../../assets/styles/varibles.less";
.list {
  display: flex;
  flex-direction: column;
  justify-content: center;
  position: absolute;
  top: 1.58rem;
  right: 0;
  bottom: 0;
  width: 0.4rem;
  .item {
    text-align: center;
    line-height: 0.4rem;
    color: @bgColor;
  }
}
</style>
