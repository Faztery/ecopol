<template>
  <ProjectSlider class="home relative grid grid-cols-12 place-content-center justify-center">
    <img class="absolute object-cover -m-8 z-0 min-h-screen col-span-12 justify-self-center" alt="background" src="https://images.unsplash.com/photo-1633163503689-f91bc6e48e4a?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=880&q=80">
    <div class="col-start-5 col-span-4 z-10">
        
      <h1 class="align-self-bottom text-5xl font-extrabold text-blue-600">
        ¿Cuánto pagaré al final de mes?
      </h1>
      <h2 class="text-2xl font-bold text-white"> 
        Averigua un estimado del precio de forma rápida y sencilla 😉
      </h2>
      <br><br>
      <ProjectButton><router-link to="/bill">Calcular</router-link> </ProjectButton>
    </div>
  </ProjectSlider>
</template>

<script>
// @ is an alias to /src
import ProjectSlider from '@/components/ProjectSlider.vue'
import ProjectButton from '@/components/ProjectButton.vue'

export default {
  name: 'HomeView',
  components: {
    ProjectSlider,
    ProjectButton
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