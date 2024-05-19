<script setup lang="ts">
import Items from './components/Items.vue'

import { defineComponent } from 'vue';
</script>

<script lang="ts">
export default defineComponent({
    props : ['prices'],
    data(){
        return{
            itemlist : [
                {
                    price:5,
                    text:'Bunga mawar - satuan / per tangkai',
                    url:'/src/assets/mawar.jpg'
                },
                {
                    price:6,
                    text:'Bunga melati - satuan / per tangkai',
                    url:'/src/assets/melati.jpg'
                },
                {
                    price:22,
                    text:'Bouqette wisuda polosan',
                    url:'/src/assets/bouqet-normal.jpg'
                },
                {
                    price:35,
                    text:'Bouqette wisuda + coklat silverqueen',
                    url:'/src/assets/bouqet-silver.jpeg'
                },
                {
                    price:40,
                    text:'Bouqette wisuda + snack ringan',
                    url:'/src/assets/bouqet-snack.jpg'
                },
                {
                    price:60,
                    text:'Bouqette wisuda + Uang tunai 20ribu x2',
                    url:'/src/assets/bouqet-uang.jpg'
                }
            ],
            searchText : ''
        }
    },
    methods: {
        filteredList() {
            return this.itemlist.filter(data => data.text.toLowerCase().includes(this.searchText.toLowerCase()))
        },
        confirmBuy(text:string, price:number){
            var database = JSON.parse(sessionStorage.getItem('items')|| '[]')
            var unique = true
            for (let i = 0; i < database.length; i++){
                if (database[i].text == text){
                    database[i].quantity += 1
                    unique = false
                }
            }
            if (unique){
                var data = {
                'price' : price,
                'text' : text,
                'quantity' : 1
                }
                database.push(data)
            }
            sessionStorage.setItem('items', JSON.stringify(database));
            this.$emit('confirm','dashboard')
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
            <input class="w-5/6 rounded-full px-5 py-1 border-2" type="text" name="text-input" id="text-input" placeholder="Cari produk anda disini." v-model="searchText">
            <input class="w-1/6 ml-4 bg-green-500 rounded-full py-1 px-8 font-semibold text-white hover:cursor-pointer" type="submit" name="submit" id="submit" value="Search">
        </form>
    </div>
    <div class="content grid-cols-5 grid mt-8 gap-3">
        <div class="card" v-for="items in filteredList()" v-show="items.price < prices" @click="confirmBuy(items.text, items.price)">
            <Items :title="items.text" :price="items.price" :url="items.url"/>
        </div>
    </div>
    
</div>
</template>

<style scoped lang="postcss">
.card {
    @apply shadow-sm border-2 rounded-md hover:shadow-md hover:shadow-green-300 hover:cursor-pointer
}
</style>