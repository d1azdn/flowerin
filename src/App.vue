<script setup lang="ts">
import Topbar from './pages/components/Topbar.vue'
import Navbar from './pages/components/Navbar.vue'
import Dashboard from './pages/Dashboard.vue'
import Cart from './pages/Cart.vue'
import About from './pages/About.vue'
//import HelloWorld from './components/HelloWorld.vue'
//ini taruh di template<HelloWorld msg="Vite + Vue" />
</script>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
    data(){
        return{
            price : 200,
            menu : 'dashboard',
        }
    },
    methods: {
        priceChange(prices:number){
          this.price = prices
        },
        menuChange(menus:string){
          this.menu = menus
        }
    }
})
</script>

<template>
  <Topbar/>
  <div class="mx-12 mt-6 flex flex-row">
    <Navbar @price="priceChange" @menu="menuChange"/>
    <Dashboard v-show="menu=='dashboard'" :prices="price"/>
    <Cart v-show="menu=='cart'"/>
    <About v-show="menu=='about'"/>
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
