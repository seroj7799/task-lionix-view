<template>
  <div id="app">
      <div>
          <b-tabs content-class="mt-3" fill>
              <b-tab title="Cities" active>
                  <CitiesTable></CitiesTable>
              </b-tab>
              <b-tab title="Weather of cities">
                  <WeatherTable></WeatherTable>
              </b-tab>
          </b-tabs>
      </div>

  </div>
</template>

<script>

import CitiesTable from "./components/CitiesTable";
import WeatherTable from "./components/WeatherTable";


export default {
  name: 'App',
  components: {
    CitiesTable,
    WeatherTable

  },

}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
