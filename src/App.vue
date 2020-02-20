<template lang="html">
  <div>
    <h1> List of Coutries</h1>
    <countries-list :countries='countries'></countries-list>
    <country-detail :country='selectedCountry'></country-detail>
  </div>
</template>

<script>
import {eventBus} from './main.js';
import CountriesList from './components/CountriesList.vue';
import CountryDetail from './components/CountryDetail.vue'

export default {
  name: 'app',
  data(){
    return {
      countries: [],
      selectedCountry: null

    };//ends return

  },//ends data
  mounted(){
    fetch('https://restcountries.eu/rest/v2/all')
    .then(res => res.json())
    .then(countries => this.countries = countries)

    eventBus.$on('country-selected', (country)=> {
      this.selectedCountry = country;
      //console.log('within $on', munro);
    })
  },//ends mounted
  components: {
    "countries-list": CountriesList,
    "country-detail": CountryDetail

  }//ends components
}//ends export
</script>

<style lang="css" scoped>
</style>
