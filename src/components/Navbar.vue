<template>
    <div class="bg-white flex flex-col w-1/5" id="navbar">
    
        <h1 class="py-3 text-xl font-medium">
            Filter
        </h1>
        <div class="filter flex flex-col rounded-md border-2 items-start px-4 py-3">
            <p class="pb-1 text-md font-semibold">Harga</p>
            <button class="py-2 px-5 w-full text-left text-sm rounded-md" :class="[{ 'bg-green-500 hover:bg-green-400 text-white' : harga == 10 }, 'hover:bg-gray-100' ]" @click="harga = 10">
                Rp. 0 - 10,000
            </button>
            <button class="py-2 px-5 w-full text-left text-sm rounded-md" :class="[{ 'bg-green-500 hover:bg-green-400 text-white' : harga == 25 }, 'hover:bg-gray-100' ]" @click="harga = 25">
                Rp. 10,000 - 25,000
            </button>
            <button class="py-2 px-5 w-full text-left text-sm rounded-md" :class="[{ 'bg-green-500 hover:bg-green-400 text-white' : harga == 50 }, 'hover:bg-gray-100' ]" @click="harga = 50">
                Rp. 25,000 - 50,000
            </button>
            <button class="py-2 px-5 w-full text-left text-sm rounded-md" :class="[{ 'bg-green-500 hover:bg-green-400 text-white' : harga == 100 }, 'hover:bg-gray-100' ]" @click="harga = 100">
                Rp. 50,000 ++
            </button>
        </div>

        <div class="desc flex flex-col mt-2">
            <button class="text-md text-start py-2 px-4 rounded-md" :class="[{'bg-green-500 hover:bg-green-400 text-white' : halaman == 'dashboard' }, 'hover:bg-gray-100' ]">
                Dashboard
            </button>
            <button class="text-md text-start py-2 px-4 hover:bg-gray-100">
                Keranjang Saya
            </button>
            <button class="text-md text-start py-2 px-4 hover:bg-gray-100">
                About
            </button>
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