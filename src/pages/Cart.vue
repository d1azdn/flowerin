<template>
    <div class="ml-8 w-full">
        <h1 class="py-3 text-xl font-medium">Produk yang anda beli</h1>
        <div class="content w-full shadow-sm border-2 rounded-md">
            <div class="itemlist w-full flex px-4 items-center">
                <div class="images flex justify-center content-center">
                    <img src="/src//assets/Logo-black.png" class="w-24 my-6" alt="">
                </div>
                <div class="desc p-4">
                    <p class="font-light">
                        Bunga mawar - satuan
                    </p>
                    <h1 class="font-semibold">
                        Rp.5,000
                    </h1>
                    <h1 class="text-2xl">x2</h1>
                </div>
            </div>
            <div class="itemlist w-full flex px-4 items-center">
                <div class="images flex justify-center content-center">
                    <img src="/src//assets/Logo-black.png" class="w-24 my-6" alt="">
                </div>
                <div class="desc p-4">
                    <p class="font-light">
                        Bunga mawar - satuan
                    </p>
                    <h1 class="font-semibold">
                        Rp.5,000
                    </h1>
                    <h1 class="text-2xl">x3</h1>
                </div>
            </div>
        </div>

        <div class="total mt-4 text-end flex justify-end">
            <div class="total-text">
                <p>Total Harga</p>
                <h1 class="font-semibold text-2xl">Rp. 25,000</h1>
            </div>
            <button class="ml-6 bg-green-500 font-semibold px-8 py-2 rounded-lg text-xl text-white hover:bg-green-400">Bayar</button>
        </div>
    </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
    data(){
        return{
            harga : 10,
            halaman : 'dashboard',
        }
    },
    methods: {
        turnOn(){ 
        }
    }
})
</script>