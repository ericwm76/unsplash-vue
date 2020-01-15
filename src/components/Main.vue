<template>
  <main id="main">
    <div v-for="photo in photos" :key="photo.id">
      <img v-bind:src="photo.urls.full" v-bind:alt="photo.alt_description" />
    </div>
  </main>
</template>

<script>
export default {
  name: 'main',
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