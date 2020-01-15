<template>
  <main id="main-container">
    <div v-for="photo in photos" :key="photo.id">
      <img v-bind:src="photo.urls.small" v-bind:alt="photo.alt_description" />
    </div>
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
  padding: 10px;
  margin: 0 10%;
  width: 100%;
}
img {
  align-items: center;
  border: 1px solid lightgrey;
  border-radius: 1px;
  height: 270px;
  width: 405px;
}

</style>