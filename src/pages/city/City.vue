<template>
  <div>
    <city-header></city-header>
    <city-search></city-search>
    <city-list
      :hot = "hotCities"
      :cities = "cities"
    ></city-list>
    <city-alphabet
      :cities = "cities"
    ></city-alphabet>
  </div>
</template>
<script>
import axios from 'axios'
import CityHeader from './components/Header'
import CitySearch from './components/Search'
import CityList from './components/List'
import CityAlphabet from './components/Alphabet'
export default {
  name: 'City',
  components: {
    CityHeader,
    CitySearch,
    CityList,
    CityAlphabet
  },
  data () {
    return {
      hotCities: [],
      cities: {}
    }
  },
  methods: {
    getHomeInfo () {
      axios.get('/api/city.json')
        .then(this.getHomeInfoSucc)
    },
    getHomeInfoSucc (res) {
      if (res.data.ret && res.data.data) {
        const data = res.data.data
        this.cities = data.cities
        this.hotCities = data.hotCities
        console.log(data)
      }
    }
  },
  mounted () {
    this.getHomeInfo()
  }
}

</script>
<style lang="stylus" scope>

</style>
