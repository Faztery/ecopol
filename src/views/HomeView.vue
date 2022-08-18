<template>
  <ProjectSlider class="home relative">
    <img class="absolute object-cover" alt="background" src="https://images.unsplash.com/photo-1633163503689-f91bc6e48e4a?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=880&q=80">
    <nav class="absolute bottom-0">
      <router-link to="/">Home</router-link> |
      <router-link to="/bill">About</router-link>
    </nav>
  </ProjectSlider>
</template>

<script>
// @ is an alias to /src
import ProjectSlider from '@/components/ProjectSlider.vue'

export default {
  name: 'HomeView',
  components: {
    ProjectSlider
  }
}
</script>
<style scoped>
nav {
  padding: 30px;
}

nav a {
  font-weight: bold;
  color: #2c3e50;
}

nav a.router-link-exact-active {
  color: #42b983;
}
</style>