<template>
  <div id="app">
    <header class="d-flex justify-content-between align-items-center">
      <h1 class="px-3">BOOLFLIX</h1>
      <search-bar
        class="px-3"
        @search="searchContent" />
    </header>
    <main-container 
    :movies="movieList"
    :series="tvList"/>
  </div>
</template>

<script>
import axios from 'axios'
import SearchBar from './components/SearchBar.vue'
import MainContainer from './components/MainContainer.vue'

export default {
  name: 'App',
  components: {
    SearchBar,
    MainContainer
  },
  data() {
    return {
      movieList: [],
      tvList: []
    }
  },
  methods: {

    searchMovies(input) {
      axios.get(`https://api.themoviedb.org/3/search/movie?api_key=12b92aed85e20971f9d1ef915a4fd61d&query=${input}`).then((response) => {
        this.movieList = response.data.results;
        return this.movieList;
      })
    },

    seachTV(input) {
       axios.get(`https://api.themoviedb.org/3/search/tv?api_key=12b92aed85e20971f9d1ef915a4fd61d&query=${input}`).then((response) => {
        this.tvList = response.data.results;
        return this.tvList;
       })
    },

    searchContent(input) {
      this.searchMovies(input);
      this.seachTV(input);
    },
  }
}
</script>

<style lang="scss">
  @import "./style/main.scss";

  header {
    background-color: #000000;
    width: 100%;

    h1 {
      color: #c60000;

    }
  }

  
</style>
