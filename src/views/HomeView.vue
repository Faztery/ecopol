<template>
  <ProjectSlider class="home min-h-screen relative bg-green-600 overflow-hidden flex">
    <img class="absolute object-cover -m-8 z-0 h-full justify-self-center" alt="background" src="https://images.unsplash.com/photo-1451187580459-43490279c0fa?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1744&q=80">
    <div class="absolute bg-[#000000] bg-opacity-40  top-0 bottom-0 right-0 left-0  -m-8 z-10 pt-8 flex flex-col justify-center items-center">
        
      <img class="h-60 rounded" src="../assets/ecopol.png"/>

      <h3 class="mt-[10vh] w-screen z-10 text-4xl font-extrabold text-gray-100 text-center">
        ¿Cuánto pagaré al final de mes?
      </h3>
      
      <ProjectButton class="z-10 mt-12 text-xl px-12 py-4 font-bold"><router-link class="focus:outline-none" to="/bill">Descúbrelo</router-link> </ProjectButton>
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