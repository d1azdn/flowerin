<script setup lang="ts">
import Topbar from './pages/components/Topbar.vue'
import Navbar from './pages/components/Navbar.vue'
import Confirm from './pages/components/Confirm.vue'
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
            confirmation : false,
            confirmTitle : 'Selesai !',
            confirmText : 'Item telah masuk kedalam keranjang.'
        }
    },
    methods: {
        priceChange(prices:number){
          this.price = prices
        },
        menuChange(menus:string){
          this.menu = menus
        },
        confirmMenu(text:string){
          this.confirmation = true
          if (text == 'dashboard'){
            this.confirmTitle = 'Selesai !'
            this.confirmText = 'Item telah masuk kedalam keranjang.'
          } else {
            this.confirmTitle = 'Pembelian sukses !'
            this.confirmText = 'Terimakasih telah berbelanja di kami.'
          }
        },
        hideConfirm(){
          this.confirmation = false
        }
    }
})
</script>

<template>
  <Confirm v-show="confirmation" @hide="hideConfirm" :title="confirmTitle" :text="confirmText"/>
  <Topbar/>
  <div class="mx-12 mt-6 flex flex-row">
    <Navbar @price="priceChange" @menu="menuChange"/>
    <Dashboard v-show="menu=='dashboard'" :prices="price" @confirm="confirmMenu"/>
    <Cart v-show="menu=='cart'" @confirm="confirmMenu"/>
    <About v-show="menu=='about'"/>
  </div>
</template>

<style>
</style>
