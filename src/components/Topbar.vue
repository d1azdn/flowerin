<template>
    <div class="topbar bg-gray-200 py-2 font-light text-sm text-gray-600 px-4 flex justify-between">
        <div class="copyright">
        <p>Copyright 2024, Flowerin' apps.</p>
        </div>
        <div class="socials flex flex-row">
        <p class="px-4 hover:text-green-500 hover:cursor-pointer">Github pages</p>
        <p class="px-4 hover:text-green-500 hover:cursor-pointer">Linkedin</p>
        <p class="px-4 hover:text-green-500 hover:cursor-pointer">Instagram</p>
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