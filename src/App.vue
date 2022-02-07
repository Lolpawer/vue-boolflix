<template>
  <div id="app">
    <header-box class="d-flex justify-content-between align-items-center"
    @search="searchContent"  />
    <main-container 
    :movies="movieList"
    :series="tvList"/>
  </div>
</template>

<script>
import axios from 'axios'
import HeaderBox from './components/HeaderBox.vue'
import MainContainer from './components/MainContainer.vue'

export default {
  name: 'App',
  components: {
    HeaderBox,
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

    searchPopularMovies() {
      axios.get(`https://api.themoviedb.org/3/movie/popular?api_key=12b92aed85e20971f9d1ef915a4fd61d`).then((response) => {
        this.movieList = response.data.results;
        return this.movieList;
      })
    },

    searchPopularTv() {
      axios.get(`https://api.themoviedb.org/3/tv/popular?api_key=12b92aed85e20971f9d1ef915a4fd61d`).then((response) => {
        this.tvList = response.data.results;
        return this.tvList;
      })
    },
  },
  mounted() {

    this.searchPopularMovies();
    this.searchPopularTv()
  }
}
</script>

<style lang="scss">
  @import "./style/main.scss";
</style>
