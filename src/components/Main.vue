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
img {
  height: 360px;
  width: 480px;
}

</style>