<template lang="html">
<div>
  <li v-on:click="handleClick">{{country.name}}</li>
</div>
</template>

<script>



export default {
  name: 'list-item',
  props: ['country'],

  methods: {
    handleClick: function(){
      eventBus.$emit('country-selected', this.country)
    }
  }






}
</script>

<style lang="css" scoped>
</style>
