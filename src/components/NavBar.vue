<template>
  <nav id="nav-bar">
    <h1 id="header">FotoFindur!</h1>
    <h2 id="subheader">Find ur fotos!</h2>
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
  background-color: rgb(255, 234, 139);
  margin: 0;
}

#header {
  font-family: 'Pacifico', cursive;
  margin: 0;
}

#subheader {
  font-family: 'Quicksand', sans-serif;
  margin: 0;
}

form {
  display: flex;
  justify-content: center;
  align-items: center;
}

input {
  display: inline-block;
  height: 50px;
  margin: 0 20px;
  width: 25%;
}

button {
  display: inline-block;
  height: 50px;
  margin: 0;
  width: 15%;
}
</style>