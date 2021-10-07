<template>
  <div id="app">
    <Header @search="searchFilm"/>
    <Films :films="films" :tvSeries="tvSeries"/>
  </div>
</template>

<script>
import Header from './components/Header.vue';
import Films from './components/Films.vue';
import axios from 'axios';

export default {
  name: 'App',
  components: {
    Header,
    Films
  },
  data() {
    return {
      films:[],
      tvSeries:[]
    }
  },
  methods: {
    searchFilm(query) {
      axios.get('https://api.themoviedb.org/3/search/movie', {
        params: {
          api_key: '6e1f2787601fcd4236204e683f91fbbf',
          query: query,
          language: 'it-IT',
        }
      })
        .then( (response) => {
          this.films = response.data.results;
        });
        axios.get('https://api.themoviedb.org/3/search/tv', {
        params: {
          api_key: '6e1f2787601fcd4236204e683f91fbbf',
          query: query,
          language: 'it-IT',
        }
      })
        .then( (response) => {
          this.tvSeries = response.data.results;
        });
    },
  }
}
</script>

<style lang="scss">
@import './assets/style/common';

</style>