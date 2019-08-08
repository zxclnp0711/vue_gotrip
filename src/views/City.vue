<template>
  <div class="">
    <city-header></city-header>
    <city-search :cities="cities"></city-search>
    <city-list :cities="cities"
               :hot="hotCities"
               :letter="letter"></city-list>
    <city-alphabet :cities="cities"
                   @change="handleLetterChange"></city-alphabet>
  </div>
</template>
<script>
import CityHeader from '../components/city/Header'
import CitySearch from '../components/city/Search'
import CityList from '../components/city/List'
import CityAlphabet from '../components/city/Alphabet'
export default {
  data () {
    return {
      cities: {},
      hotCities: [],
      letter: ''
    }
  },
  components: {
    CityHeader,
    CitySearch,
    CityList,
    CityAlphabet
  },
  mounted () {
    this.getCityInfo()
  },
  created () { },
  methods: {
    async getCityInfo () {
      let res = await this.$axios.get('/api/city.json')
      console.log(res)
      res = res.data
      if (res.ret && res.data) {
        const data = res.data
        this.cities = data.cities
        this.hotCities = data.hotCities
      }
    },
    handleLetterChange (letter) {
      this.letter = letter
    }
  }
}
</script>
<style lang="less" scoped>
</style>
