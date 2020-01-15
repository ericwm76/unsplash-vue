<template>
  <nav id="nav-bar">
    <h1 id="header">FotoFindur</h1>
    <h2 id="subheader">find ur fotos</h2>
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
    handleSubmit(e) {
      e.preventDefault();
      this.$emit('update:searchTerm', this.searchTerm)
    }
  }
}

</script>

<style scoped>
nav {
  background-color: rgb(212, 193, 109);
  border-bottom: 3px solid lightgray;
  margin: 0;
  padding: 20px;
}

#header {
  font-family: 'Pacifico', cursive;
  font-size: 4em;
  margin: 10px;
}

#subheader {
  font-family: 'Quicksand', sans-serif;
  margin: 10px;
}

form {
  display: flex;
  justify-content: center;
  align-items: center;
}

input {
  background-color: antiquewhite;
  display: inline-block;
  height: 50px;
  margin: 0 20px;
  width: 25%;
}

button {
  background-color: steelblue;
  display: inline-block;
  height: 50px;
  margin: 0;
  width: 15%;
}
</style>