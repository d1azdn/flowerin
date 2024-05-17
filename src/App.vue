<script setup lang="ts">
import Topbar from './components/Topbar.vue'
import Navbar from './components/Navbar.vue'
import Dashboard from './components/Dashboard.vue'
//import HelloWorld from './components/HelloWorld.vue'
//ini taruh di template<HelloWorld msg="Vite + Vue" />
</script>

<template>
  <Topbar/>
  <div class="mx-12 mt-6 flex flex-row">
    <Navbar/>
    <Dashboard/>
  </div>
</template>

<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
