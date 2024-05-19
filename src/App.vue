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
let loadPages = sessionStorage.getItem('load' || [])

import { defineComponent } from 'vue';

export default defineComponent({
    data(){
        return{
            price : 200,
            menu : 'dashboard',
            confirmation : false,
            confirmTitle : 'Selesai !',
            confirmText : 'Item telah masuk kedalam keranjang.',
            loadingState : false,
            loadingState1 : false,
            main : loadPages,
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
        },
        loadingAnimation(){
          sessionStorage.setItem('load','1')
          this.loadingState = true
          setTimeout(()=> {
            this.loadingState = false
            this.loadingState1 = true
          }, 3000)
          this.loadingState1 = false
          setTimeout(()=>{
            this.main = '1'
          }, 3000)
        }
    }
})
</script>

<template>
  <div class="pb-20" v-show="main=='1'">

    <div class="loadingin w-full h-full text-center flex fixed justify-center content-center items-center bg-green-500 z-30" style="animation: slideOut 1s forwards;" v-if="loadingState1">
      <p class="text-8xl text-white">Loading..</p>
    </div>

    <Confirm v-show="confirmation" @hide="hideConfirm" :title="confirmTitle" :text="confirmText"/>
    <Topbar/>
    <div class="mx-12 mt-6 flex flex-row">
      <Navbar @price="priceChange" @menu="menuChange"/>
    <Dashboard v-show="menu=='dashboard'" :prices="price" @confirm="confirmMenu"/>
    <Cart v-show="menu=='cart'" @confirm="confirmMenu"/>
    <About v-show="menu=='about'"/>
  </div>
</div>  

  <div class="mainpage w-full h-full justify-center content-center items-center text-center flex flex-col fixed z-10">
    
    <div class="loadingin w-full h-full text-center flex fixed justify-center content-center items-center bg-green-500 z-20" style="animation: slideIn 1s forwards;" v-if="loadingState">
      <p class="text-8xl text-white">Loading..</p>
    </div>

    <div class="images">
      <img src="/src/assets/Logo-black.png" class="w-64" alt="">
    </div>

    <h1 class="text-4xl font-semibold my-2">Flowerin'</h1>
    <p class="text-2xl mb-6">Pusat bunga segar di Jakarta !</p>
    <div class="buttonsection">
      <a href="https://github.com/d1azdn/flowerin" target="_blank">
        <button class="bg-white border-2 border-green-500 rounded-full text-black text-xl text-center py-2 px-8 mx-2 hover:scale-110 transition-all duration-500">Lihat di GitHub -></button>
      </a>
      <button class="bg-green-500 rounded-full text-white text-2xl text-center py-2 px-8 mx-2 hover:scale-110 transition-all duration-500" @click="loadingAnimation()">Masuk ke Dashboard</button>
    </div>

  </div>
    
    <div class="area" v-if="main!='1'">
      <ul class="circles">
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
      </ul>
    </div>

</template>

<style>
.context {
    width: 100%;
    position: absolute;
    top:50vh;
    
}

.context h1{
    text-align: center;
    color: #fff;
    font-size: 50px;
}


.area{
    background: #ffffff;  
    background: -webkit-linear-gradient(to left, #8f94fb, #4e54c8);  
    width: 100%;
    height:100vh;
    
   
}

.circles{
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    overflow: hidden;
}

.circles li{
    position: absolute;
    display: block;
    list-style: none;
    width: 20px;
    height: 20px;
    background: rgb(34 197 94);
    animation: animate 25s linear infinite;
    bottom: -150px;
    
}

.circles li:nth-child(1){
    left: 25%;
    width: 80px;
    height: 80px;
    animation-delay: 0s;
}


.circles li:nth-child(2){
    left: 10%;
    width: 20px;
    height: 20px;
    animation-delay: 2s;
    animation-duration: 12s;
}

.circles li:nth-child(3){
    left: 70%;
    width: 20px;
    height: 20px;
    animation-delay: 4s;
}

.circles li:nth-child(4){
    left: 40%;
    width: 60px;
    height: 60px;
    animation-delay: 0s;
    animation-duration: 18s;
}

.circles li:nth-child(5){
    left: 65%;
    width: 20px;
    height: 20px;
    animation-delay: 0s;
}

.circles li:nth-child(6){
    left: 75%;
    width: 110px;
    height: 110px;
    animation-delay: 3s;
}

.circles li:nth-child(7){
    left: 35%;
    width: 150px;
    height: 150px;
    animation-delay: 7s;
}

.circles li:nth-child(8){
    left: 50%;
    width: 25px;
    height: 25px;
    animation-delay: 15s;
    animation-duration: 45s;
}

.circles li:nth-child(9){
    left: 20%;
    width: 15px;
    height: 15px;
    animation-delay: 2s;
    animation-duration: 35s;
}

.circles li:nth-child(10){
    left: 85%;
    width: 150px;
    height: 150px;
    animation-delay: 0s;
    animation-duration: 11s;
}



@keyframes animate {

    0%{
        transform: translateY(0) rotate(0deg);
        opacity: 1;
        border-radius: 0;
    }

    100%{
        transform: translateY(-1000px) rotate(720deg);
        opacity: 0;
        border-radius: 50%;
    }

}
@keyframes slideIn {
    from {
      transform: translateX(100%);
    }
    to {
      transform: translateX(0);
    }
  }
@keyframes slideOut {
    from {
      transform: translateX(0);
    }
    to {
      transform: translateX(100%);
    }
  }
</style>
