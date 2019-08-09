<template>
  <div>
    <detail-banner></detail-banner>
    <detail-header></detail-header>
    <div class="content"></div>
  </div>
</template>
<script>
import DetailBanner from '../components/detail/Banner'
import DetailHeader from '../components/detail/Header'
export default {
  data () {
    return {
    }
  },
  created () { },
  methods: {},
  components: {
    DetailBanner,
    DetailHeader
  }
}
</script>
<style lang="less" scoped>
.content {
  height: 50rem;
}
</style>
