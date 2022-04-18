<script>
import mapboxgl from 'mapbox-gl'; // or "const mapboxgl = require('mapbox-gl');"
export default {
  data: function () {
    return {
      message: "Welcome to Vue.js!",
    };
  },
  mounted: function () {
    this.makeMap();
  },
  methods: {
    makeMap: function () {
      mapboxgl.accessToken = process.env.VUE_APP_MAPBOX_KEY;
      const map = new mapboxgl.Map({
        container: 'map', // container ID
        style: 'mapbox://styles/mapbox/streets-v11', // style URL
        center: [-73.9859723, 40.6701033], // starting position [lng, lat]
        zoom: 12 // starting zoom
      });
    }
  },
};
</script>

<template>
  <div class="home">
    <h1>{{ message }}</h1>
    <button v-on:click="makeMap()">Make Map</button>
    <div id='map' style='width: 800px; height: 600px;'></div>

  </div>
</template>

<style>
</style>
