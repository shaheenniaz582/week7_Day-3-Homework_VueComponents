<template lang="html">
  <div>
    <ul>
      <list-item v-for="(country,index) in countries" :country="country" :key="index"></list-item>
    </ul>
  </div>
</template>

<script>
import ListItem from './ListComponent.vue';
export default {
  name: 'countries-list',
  props: ['countries'],
  components:{
    'list-item': ListItem
  }//ends compnents
}//ends export
</script>

<style lang="css" scoped>
</style>
