<template>
  <div>
    <div class="search">
      <input v-model="keyword"
             type="text"
             placeholder="输入城市名或拼音"
             class="search-input">
    </div>
    <div class="search-content"
         ref="search"
         v-show="keyword">
      <ul>
        <li v-for="item in list"
            class="search-item boder-bottom"
            :key="item.id"
            @click="handleCityClick(item.name)">
          {{item.name}}
        </li>
        <li class="search-item boder-bottom"
            v-show="!list.length">
          没有找到匹配数据
        </li>
      </ul>
    </div>
  </div>
</template>
<script>
import Bscroll from 'better-scroll'
import {mapMutations} from 'vuex'
export default {
  data () {
    return {
      keyword: '',
      list: [],
      timer: null
    }
  },
  props: {
    cities: Object
  },
  watch: {
    keyword () {
      if (!this.keyword) {
        this.list = []
        return
      }
      if (!this.timer) {
        this.timer = setTimeout(() => {
          const result = []
          for (let i in this.cities) {
            this.cities[i].forEach((value) => {
              if (value.spell.indexOf(this.keyword) > -1 || value.name.indexOf(this.keyword) > -1) {
                result.push(value)
              }
            })
          }
          this.timer = null
          clearTimeout(this.timer)
          this.list = result
        }, 100)
      }
    }
  },
  created () { },
  mounted () {
    this.scroll = new Bscroll(this.$refs.search)
  },
  methods: {
    handleCityClick (city) {
      this.changeCity(city)
      this.$router.push('/')
    },
    ...mapMutations(['changeCity'])
  }
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
.search-content {
  overflow: hidden;
  position: absolute;
  top: 1.58rem;
  left: 0;
  right: 0;
  bottom: 0;
  background: #eee;
  z-index: 1;
  .search-item {
    line-height: 0.62rem;
    padding-left: 0.2rem;
    background: #fff;
    color: #666;
  }
}
</style>
