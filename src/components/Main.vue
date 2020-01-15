<template>
  <main id="main">
    <div v-for="photo in photos" :key="photo.id">

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

</style>