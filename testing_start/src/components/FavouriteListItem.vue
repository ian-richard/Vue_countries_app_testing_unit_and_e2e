<template lang="html">
  <div id="favourite_countries">
    <h2>Favourite Countries</h2>
    <ul>
      <li v-for="(favouriteCountry, index) in favouriteCountries">{{favouriteCountry.name}} 
        <img class="small-flag" :src="favouriteCountry.flag"/>
      <button v-on:click="handleDelete(index)">Remove from favs</button></li>
    </ul>
  </div>
</template>

<script>
  import {eventBus} from '@/main.js';

export default {
  name: 'favourite-countries',
  props: ['favouriteCountries'],
  methods: {
    handleDelete: function(index) {
      eventBus.$emit('country-deleted', index);
    }
  }
}
</script>

<style lang="css" scoped>
</style>
