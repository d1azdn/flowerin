<template>
    <div class="ml-8 w-full">
        <h1 class="py-3 text-xl font-medium">Produk yang anda beli</h1>
        <div class="content w-full shadow-sm border-2 rounded-md">

            <div class="itemlist w-full flex px-4 items-center" v-for="data in datas">
                <div class="desc p-4">
                    <p class="font-light">
                        {{ data.text }}
                    </p>
                    <h1 class="font-semibold">
                        Rp.{{ data.price }},000
                    </h1>
                    <h1 class="text-2xl">x{{ data.quantity }}</h1>
                </div>
            </div>
        </div>

        <div class="total mt-4 text-end flex justify-end">
            <div class="total-text">
                <p>Total Harga</p>
                <h1 class="font-semibold text-2xl">Rp. {{ total }},000</h1>
            </div>
            <button class="ml-6 bg-green-500 font-semibold px-8 py-2 rounded-lg text-xl text-white hover:bg-green-400" @click="bayarPesanan()">Bayar</button>
        </div>
    </div>
</template>

<script lang="ts">
var database = JSON.parse(sessionStorage.getItem('items')|| '[]')
let totalPrice = 0
for (let i = 0; i < database.length;i++){
    totalPrice += database[i].quantity * database[i].price
}

import { defineComponent } from 'vue';

export default defineComponent({
    data(){
        return{
            datas : database,
            total : totalPrice
        }
    },
    methods: {
        bayarPesanan(){
            sessionStorage.removeItem('items');
            this.$emit('confirm', 'cart')
        }
    }
})
</script>