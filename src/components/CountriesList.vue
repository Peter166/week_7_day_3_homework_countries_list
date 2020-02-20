<template lang="html">
<div>
<select v-on:change="handleClik1" v-model="selectedCountry">
  <option value="" disabled>Please Choose One</option>
  <option v-for="(country, index) in countries" :key="index" :value="country">{{country.name}}</option>
</select>



  <!-- <list-item v-for="(country, index) in countries" :country='country' :key="index"></list-item> -->




</div>
</template>

<script>
import ListItem from './ListItem.vue';
import { eventBus } from '../main.js'

export default {
  name: 'countries-list',
  props: ['countries'],
  data(){
    return {
      selectedCountry: null
    }
  },
  components: {
    'list-item': ListItem
  },
methods: {
  handleClik1: function(){
    eventBus.$emit('country-selected', this.selectedCountry)
  }
}
}
</script>

<style lang="css" scoped>
</style>
