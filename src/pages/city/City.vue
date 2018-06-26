<template>
  <div>
    <city-header></city-header>
    <city-search :allCities='allCities'></city-search>
    <city-list :hotCities='hotCities' :allCities='allCities' :letter='letter'></city-list>
    <city-alphabet :allCities='allCities' @change="handleLetterChange"></city-alphabet>
  </div>
</template>

<script>
import CityHeader from './components/Header'
import CitySearch from './components/Search'
import CityList from './components/List'
import CityAlphabet from './components/Alphabet'
import axios from 'axios'
export default {
  name: 'City',
  data () {
    return {
      hotCities: [],
      allCities: {},
      letter: ''
    }
  },
  components: {
    CityHeader,
    CitySearch,
    CityList,
    CityAlphabet
  },
  methods: {
    getCityInfo () {
      axios.get('/api/city.json')
        .then(this.handleGetCitySucc)
    },
    handleGetCitySucc (res) {
      res = res.data
      if (res.data && res.ret) {
        this.hotCities = res.data.hotCities
        this.allCities = res.data.cities
      }
      console.log(res)
    },
    handleLetterChange (letter) {
      this.letter = letter
    }
  },
  mounted () {
    this.getCityInfo()
  }
}
</script>

<style lang="stylus" scoped>
</style>
