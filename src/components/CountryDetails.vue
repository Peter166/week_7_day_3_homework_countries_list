<template lang="html">
<div class="main-container"v-if="country">
  <h3>{{country.name}}</h3>
  <p>Capital: {{country.capital}}</p>
  <p>Population: {{country.population}}</p>
  <img class="flag":src="country.flag"/>
  <p v-for="(language, index) in country.languages">{{language.name}}</p>




</div>
</template>

<script>
export default {
  name: 'country-detail',
  props: ['country']
}
</script>

<style lang="css" scoped>
.aaa{
  border-style: double;
  position: fixed;
  right: 20px;
  top: 20px;
}

.main-container {
  display: flex;
  justify-content: space-between;
}


.flag {
  width: 20%;
}

</style>
