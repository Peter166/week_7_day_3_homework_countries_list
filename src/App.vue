<template lang="html">
  <div >
    <h1>Countries</h1>


    <countries-list :countries='countries'></countries-list>


    <country-detail :country='selectedCountry'></country-detail>





  </div>
</template>

<script>
import CountriesList from './components/CountriesList.vue';
import { eventBus } from './main.js'
import CountryDetails from './components/CountryDetails.vue';




export default {
  name: 'app',
  data(){
    return {
      countries: [],
      selectedCountry: null
    }
  },

  mounted(){
    fetch('https://restcountries.eu/rest/v2/all')
    .then(res => res.json())
    .then(data => this.countries = data)

    eventBus.$on('country-selected', (country)=> {
      this.selectedCountry = country;

    eventBus.$on('country-selected1', (country)=>{
      this.selectedCountry = country;
    })
    })
  },

  components: {
    'countries-list': CountriesList,
    'country-detail': CountryDetails

  }






}

</script>

<style lang="css" scoped>

.main-container {
  display: flex;
  justify-content: space-between;
}


</style>
