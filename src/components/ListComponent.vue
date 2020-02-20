<template lang="html">
  <li v-on:click="handleClick">{{country.name}}</li>
</template>

<script>
import { eventBus } from '../main.js'
export default {
  name:'list-item', // particular bullet(country name) in the country list
  props:['country'],
  methods: {
    handleClick (){
      eventBus.$emit('country-selected', this.country)
    }//ens handleclick
  }//methods
}//ends default
</script>

<style lang="css" scoped>
</style>
