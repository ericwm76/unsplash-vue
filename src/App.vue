<template>
  <div id="app">
    <NavBar/>
    <Main :photos="photos"/>
  </div>
</template>

<script>
import NavBar from './components/NavBar.vue'
import Main from './components/Main.vue'

export default {
  name: 'app',
  components: {
    NavBar,
    Main
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
    async getPhotos() {
      const apiKey = '2249e9c7aac95c641d68ecdef25d6803aca1a9ae16c60cbb8f61663fa27b2f8f'
      const url = `https://api.unsplash.com/search/photos?page=1&query=${this.searchTerm}&client_id=${apiKey}`;
      try {
        const response = await fetch(url);
        const data = await response.json();
        this.photos = data;
      } catch(error) {
        this.error = error
      }

    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
