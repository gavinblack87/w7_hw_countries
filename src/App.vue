<template>
  <div id="app">
    <h1>Countries</h1>
    <div class="all-countries">
      <country-select :countries="countries"></country-select>
      <country-detail :country="selectedCountry"></country-detail>
    </div>

  </div>
</template>

<script>
import CountrySelect from './components/CountrySelect.vue'
import CountryDetail from './components/CountryDetail.vue'
import {eventBus} from './main.js'

export default {
  name: 'app',
  data() {
    return {
      countries: [],
      selectedCountry: {}
    };
  },
  mounted() {
    fetch('https://restcountries.eu/rest/v2/all')
    .then(response => response.json())
    .then(countries => this.countries = countries)

    eventBus.$on('country-selected', (country) => {
      this.selectedCountry = country;
    })
  },
  components: {
    "country-select": CountrySelect,
    "country-detail": CountryDetail
  }

}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
