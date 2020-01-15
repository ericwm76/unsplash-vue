<template>
  <main id="main-container">
    <div v-for="photo in photos" :key="photo.id">
      <div id="image-container">
        <img v-bind:src="photo.urls.small" v-bind:alt="photo.alt_description" />
      </div>
    </div>
    <!-- <button v-if="photos.length" id="load-button">Load more</button> -->
  </main>
</template>

<script>
export default {
  name: 'MainContainer',
  props: {
    photos: Array
  }
}
</script>

<style scoped>
main {
  display: grid;
  grid-gap: 10px;
  grid-template-columns: 40% 40%;
  grid-template-rows: repeat(auto, 280px);
  padding: 10px;
  margin: 0 10%;
  width: 100%;
}
#image-container {
  height: 280px;
}

img {
  align-items: center;
  border: 1px solid lightgrey;
  border-radius: 1px;
  height: 270px;
  width: 405px;
}
img:hover {
  height: 275px;
  width: 410px;
  transition: .2s;
}

/* #load-button {
  background-color: white;
  color: steelblue;
  margin: auto;
} */

</style>