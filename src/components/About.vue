<template>
    <div class="ml-8 w-full">
        <h1 class="py-3 text-xl font-medium">Mengenai produk kami</h1>
        <div class="content w-full grid grid-col-3 gap-3">
            <div class="content border-2 shadow-sm p-4 rounded-xl h-32">
                <h1 class="text-2xl mb-2">Apa itu Flowerin' ?</h1>
                <p>Flowerin' merupakan website penjualan bunga yang menggunakan Vue JS sebagai front end, dan sessionStorage sebagai pembantu dalam memasukkan item ke keranjang.</p>
            </div>
            <div class="content border-2 shadow-sm p-4 rounded-xl h-32">
                <h1 class="text-2xl mb-2">Apa tujuan website ini ?</h1>
                <p>Website ini dibentuk untuk pembelajaran mengenai fitur fitur yang ada di vue js, dan memahami sedikit-demi sedikit mengenai Typescript.</p>
            </div>
            <div class="content border-2 shadow-sm p-4 rounded-xl h-32">
                <h1 class="text-2xl mb-2">Github Pages</h1>
                <p>Klik pada bagian ini untuk menuju ke github.com/d1azdn/flowerin</p>
            </div>
            <div class="imgdiv flex justify-center text-center flex-col items-center mt-16 mb-10">
                <img src="/src/assets/Logo-black.png" class="w-48" alt="">
                <p class="text-2xl">Hello!</p>
            </div>
        </div>
    </div>
</template>

<style scoped></style>

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