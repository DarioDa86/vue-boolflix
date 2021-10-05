<template>
  <div id="app">
    <Header @search="selectedMethod" />
    <Films :transferFilms="selectedFilms" />
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
      selectedFilms: ""
    }
  },
  methods: {
    selectedMethod(text) {
      this.selectedFilms = text;
      axios.get('https://api.themoviedb.org/3/search/movie?api_key=e99307154c6dfb0b4750f6603256716d&query=ritorno+al+futuro')
          .then( (res) => {
            this.films = res.data.results;
          } )
    }
  },
  // created() {
	// 	axios
	// 		.get("https://api.themoviedb.org/3/movie/550?api_key=6e1f2787601fcd4236204e683f91fbbf")
	// 		.then( (res) => {
	// 			this.films = res.data;
	// 		});
	// },
}
</script>

<style lang="scss">
@import './src/assets/style/common';

</style>