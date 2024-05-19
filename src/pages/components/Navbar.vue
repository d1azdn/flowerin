<template>
    <div class="bg-white flex flex-col w-1/5" id="navbar">
    
        <h1 class="py-3 text-xl font-medium">
            Filter
        </h1>
        <div class="filter flex flex-col rounded-md border-2 items-start px-4 py-3">
            <p class="pb-1 text-md font-semibold">Harga</p>

            <button v-for="(value, key) in pricelist" :class="[{ 'bg-green-500 hover:bg-green-400 text-white' : price == key }, 'hover:bg-gray-100' ]" @click="priceChange(key)">
            {{ value }}
            </button>

        </div>

        <div class="desc flex flex-col mt-2">
            <button id="dashboard" :class="[{'bg-green-500 hover:bg-green-400 text-white' : menu == 'dashboard' }, 'hover:bg-gray-100' ]" @click="menuChange('dashboard')">
                Dashboard
            </button>
            <button id="cart" :class="[{'bg-green-500 hover:bg-green-400 text-white' : menu == 'cart' }, 'hover:bg-gray-100' ]" @click="menuChange('cart')">
                Keranjang Saya
            </button>
            <button id="about" :class="[{'bg-green-500 hover:bg-green-400 text-white' : menu == 'about' }, 'hover:bg-gray-100' ]" @click="menuChange('about')">
                About
            </button>
        </div>
    </div>
</template>

<style scoped lang="postcss">
.filter button{
    @apply py-2 px-5 w-full text-left text-sm rounded-md
}

.desc button{
    @apply text-start py-2 px-4 rounded-md
}

</style>

<script lang="ts">
    import { defineComponent } from 'vue';

    export default defineComponent({
        data(){
            return{
                pricelist : 
                { 
                    10:'< Rp. 10,000',
                    25:'< Rp. 25,000',
                    50:'< Rp. 50,000',
                    100:'< Rp. 100,000', 
                    200: 'All'},

                menulist : {
                    'dashboard' : 'Dashboard',
                    'cart' : 'Keranjang Saya',
                    'about' : 'About'
                },

                price : 200,
                menu : 'dashboard',
            }
        },
        methods: {
            priceChange(data:number){
                this.price = data;
                this.$emit('price', this.price)
            },
            menuChange(menu:string){ 
                this.menu = menu;
                this.$emit('menu', this.menu)
            }
        }
    })
</script>