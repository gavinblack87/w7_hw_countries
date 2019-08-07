<template lang="html">
  <div>
    <!-- <ul>
      <country-list-item v-for="(country, index) in countries" :country="country" :key="index"></country-list-item>
    </ul> -->

    <label for="country-select">Select Country:</label>
    <select v-model="selectedCountry">
      <option disabled value="">Select Country</option>
      <option v-for="(country, index) in countries" :country="country" :key="index">{{ country.name }}</option>
    </select>

  </div>
</template>

<script>
// import CountryListItem from './CountryListItem.vue';
import { eventBus } from '../main.js';
export default {
  name: 'country-select',
  props: ['countries']
  // components: {
  //   "country-list-item": CountryListItem
  // }
}
</script>

<style lang="css" scoped>
</style>
