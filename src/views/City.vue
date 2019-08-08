<template>
  <div class="">
    <city-header></city-header>
    <city-search></city-search>
  </div>
</template>
<script>
import CityHeader from '../components/city/Header'
import CitySearch from '../components/city/Search'
export default {
  data () {
    return {
    }
  },
  components: {
    CityHeader,
    CitySearch
  },
  created () { },
  methods: {}
}
</script>
<style lang="less" scoped>
</style>
