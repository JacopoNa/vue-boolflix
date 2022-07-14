<template>
  <div id="app">
    <HeaderComponent @componentSearch="search"/>
    <MainComponent :movieCards="movies" :seriesCards="series"/>
  </div>
</template>

<script>
import axios from 'axios'
import HeaderComponent from './components/HeaderComponent.vue'
import MainComponent from './components/MainComponent.vue'

export default {
  name: 'App',
  components: {
    HeaderComponent,
    MainComponent
  },
  data: function () {
      return {
        url: 'https://api.themoviedb.org/3/search/',
        apiKey: 'f9e16a68756f4413e1205b08a8d5365a',
        movies: [],
        series: []
      }
  },
  methods: {
    getMovies(apiParams) {
      axios.get(this.url + 'movie', apiParams).then((response) => {
        this.movies = response.data.results;
      }) 
    },
    getTvSeries(apiParams) {
      axios.get(this.url + 'tv', apiParams).then((response) => {
        this.series = response.data.results;
      }) 
    },
    search: function (searchText) {
      const paramsObj = {
        params: {
          api_key: this.apiKey,
          query: searchText,
          language: 'it-IT'
        }
      };

      this.getMovies(paramsObj);
      this.getTvSeries(paramsObj);
    }
  }
}

</script>

<style lang="scss">
@import './assets/styles/common.scss'
</style>
