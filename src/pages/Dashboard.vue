<script setup lang="ts">
import Items from './components/Items.vue'

import { defineComponent } from 'vue';
</script>

<script lang="ts">

export default defineComponent({
    data(){
        return{
            itemlist : [
                {
                    title:'bungamawar',
                    price:5,
                    text:'Bunga mawar - satuan / per tangkai'
                },
                {
                    title:'bungamelati',
                    price:6,
                    text:'Bunga melati - satuan / per tangkai'
                },
                {
                    title:'bouqettewisuda',
                    price:35,
                    text:'Bouqette wisuda + coklat silverqueen'
                },
                {
                    title:'bouqettewisuda',
                    price:40,
                    text:'Bouqette wisuda + snack ringan'
                },
                {
                    title:'bouqettewisuda',
                    price:60,
                    text:'Bouqette wisuda + Uang tunai 20ribu x2'
                }
            ]
        }
    },
    methods: {
        turnOn(){ 
        }
    }
})
</script>

<template>
<div class="ml-8 w-full">
    <h1 class="py-3 text-xl font-medium">
        Cari produk anda disini</h1>
    <div class="search flex flex-row">
        <form action="javascript:;" class="w-full flex flex-row" onsubmit="">
            <img src="/src/assets/Logo-black.png" class="w-12 mr-4" alt="">
            <input class="w-5/6 rounded-full px-5 py-1 border-2" type="text" name="text-input" id="text-input" placeholder="Write your text here.">
            <input class="w-1/6 ml-4 bg-green-500 rounded-full py-1 px-8 font-semibold text-white hover:cursor-pointer" type="submit" name="submit" id="submit" value="Search">
        </form>
    </div>
    <div class="content grid-cols-5 grid mt-8 gap-3">
        <div class="card" v-for="items in itemlist">
            <Items :title="items.text" :price="items.price"/>
        </div>
    </div>
    
</div>
</template>

<style scoped lang="postcss">
.card {
    @apply shadow-sm border-2 rounded-md hover:shadow-md hover:shadow-green-300 hover:cursor-pointer
}
</style>