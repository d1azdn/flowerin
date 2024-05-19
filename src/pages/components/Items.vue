<template>
    <div class="images flex justify-center content-center">
        <img :src="url" class="w-3/4 h-32 mt-6 object-cover" alt="">
    </div>
    
    <div class="desc p-4">
        <p class="font-light break-words overflow-hidden h-20">
        {{ title }}
        </p>
        <h1 class="font-semibold">
        Rp.{{ price }},000
        </h1>
        </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
    props : ['title', 'price', 'url'],
    data(){
        return{

        }
    },
    methods: {
        turnOn(){ 
        }
    }
})
</script>