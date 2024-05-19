<template>
<div>
    <div class="text-center justify-center content-center flex items-center fixed w-full h-full z-0 hover:cursor-pointer" style="background-color: rgba(0, 0, 0, 0.3);" @click.self="hideConfirm()">
        <div class="confirm-card bg-white z-10 p-10 rounded-xl hover:cursor-default">
            <div class="images justify-center content-center flex">
                <img src="/src/assets/Logo-black.png" class="w-44 mb-4" alt="">
            </div>
            <h1 class="text-4xl font-semibold text-green-500 my-2">{{ title }}</h1>
            <p>{{ text }}</p>
        </div>
    </div>
</div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
    props : ['title', 'text'],
    data(){
        return{
        }
    },
    methods: {
        hideConfirm(){
            this.$emit('hide', false)
            window.location.reload()
        }
    }
})
</script>