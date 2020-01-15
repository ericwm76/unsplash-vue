<template>
  <nav id="nav-bar">
    <h1>FotoFindur!</h1>
    <h2>Find ur fotos!</h2>
    <form>
      <input v-model="searchTerm" type="text" placeholder="Search for photos here" />
      <button @click="handleSubmit">Submit</button>
    </form>
  </nav>  
</template>

<script>
export default {
  name: 'nav-bar',
  data() {
    return {
      searchTerm: ''
    }
  },
  methods: {
    handleSubmit() {
      this.$emit('update:searchTerm', this.searchTerm)
    }
  }
}

</script>

<style scoped>

</style>