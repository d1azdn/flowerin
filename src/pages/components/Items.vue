<template>
    <div class="images flex justify-center content-center">
        <img src="/src//assets/Logo-black.png" class="w-32 my-6" alt="">
    </div>
    
    <div class="desc p-4">
        <p class="font-light break-words overflow-hidden h-24">
        {{ title }}
        </p>
        <h1 class="font-semibold">
        Rp.{{ price }},000
        </h1>
        </div>
</template>

<style scoped lang="postcss">
.card {
    @apply shadow-sm border-2 rounded-md hover:shadow-md hover:shadow-green-300 hover:cursor-pointer
}
</style>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
    props : ['title', 'price'],
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