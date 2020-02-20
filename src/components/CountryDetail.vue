<template lang="html">
  <div v-if='country' >
    <h3>{{country.name}}</h3>
    <p>Population: {{country.population}}</p>
    <p>Region: {{country.region}}</p>
    <p>Capital: {{country.capital}}</p>
  </div>

</template>

<script>
export default {
  name: 'country-detail',
  props: ['country']
}
</script>

<style lang="css" scoped>
  div{
    position: fixed;
    top: 20px;
    right:20px;
  }
</style>
