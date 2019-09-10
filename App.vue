<script>
import MapboxMap from "./components/MapboxMap.vue";
import MapboxMarkers from "./components/MapboxMarkers.vue";
import MapboxNavigation from "./components/MapboxNavigation.vue";

export default {
  components: {
    MapboxMap,
    MapboxMarkers,
    MapboxNavigation
  },
  data() {
    return {
      cities: [
        {
          name: "Westfield",
          lat: 42.125093,
          long: -72.749538
        },
        {
          name: "s'Gravenwezel",
          lat: 51.26292,
          long: 4.56096
        },
        {
          name: "Lansing",
          lat: 42.732535,
          long: -84.555535
        },
        {
          name: "Freiburg",
          lat: "47.999008",
          long: "7.842104"
        }
      ]
    };
  }
};
</script>

<template>
  <div id="app">
    <MapboxMap
      access-token="pk.eyJ1IjoiY2hyaXN2ZnJpdHoiLCJhIjoiY2lxMjAzYW9oMDExOGZ2bm80MTI2MDh6cSJ9.cbVt5KGuKqYkI2Lx7ysIFw"
    >
      <MapboxMarkers
        :items="cities"
        primary
      >
        <template slot-scope="city">
          {{ city.name }}
        </template>
      </MapboxMarkers>
      <MapboxNavigation/>
    </MapboxMap>
  </div>
</template>

<style lang="scss">
*,
*::before,
*::after {
  box-sizing: content-box;
}

html,
body,
#app {
  height: 100%;
}
</style>
