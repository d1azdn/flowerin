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
        <div class="card shadow-sm border-2 rounded-md hover:shadow-md hover:shadow-green-300 hover:cursor-pointer">
            <div class="images flex justify-center content-center">
                <img src="/src//assets/Logo-black.png" class="w-32 my-6" alt="">
            </div>
            <div class="desc p-4">
                <p class="font-light">
                    Bunga mawar - satuan
                </p>
            <h1 class="font-semibold">
                Rp.5,000
            </h1>
            </div>
        </div>
        
    </div>
    
</div>
</template>

<style scoped>
</style>

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