<template>
  <div id="app">
    <NavBar @update:searchTerm="updateSearchTerm"/>
    <MainContainer :photos="photos"/>
  </div>
</template>

<script>
import NavBar from './components/NavBar.vue'
import MainContainer from './components/Main.vue'

export default {
  name: 'app',
  components: {
    NavBar,
    MainContainer
  },
  data() {
    return {
      photos: [

      ],
      searchTerm: '',
      error: ''
    }
  },
  methods: {
    updateSearchTerm(searchTerm) {
      this.searchTerm = searchTerm;
      this.getPhotos(searchTerm)
    },
    async getPhotos(searchTerm) {
      const apiKey = '2249e9c7aac95c641d68ecdef25d6803aca1a9ae16c60cbb8f61663fa27b2f8f'
      const url = `https://api.unsplash.com/search/photos?page=1&query=${searchTerm}&client_id=${apiKey}`;
      try {
        const response = await fetch(url);
        const data = await response.json();
        this.photos = data.results;
      } catch(error) {
        this.error = error
      }

    }
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css?family=Pacifico|Quicksand&display=swap');

#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  box-sizing: border-box;
}
</style>
