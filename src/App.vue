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
      const url = 'https://api.unsplash.com/search/photos?page=1&query=office';
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
