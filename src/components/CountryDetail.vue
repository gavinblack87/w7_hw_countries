<template lang="html">
  <div v-if="country">
    <h3>{{ country.name }}</h3>
    <p>Capital: {{ country.capital }}</p>
    <p>Population: {{ country.population }}</p>
    <p>Region: {{ country.region }}</p>

  </div>

</template>

<script>
import { eventBus } from '../main.js';

export default {
  name: 'country-detail',
  props: ['country']
}
</script>

<style lang="css" scoped>
</style>
