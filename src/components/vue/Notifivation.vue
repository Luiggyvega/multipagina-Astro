<script setup>
import { ref } from 'vue';
let qty = ref(0);

function add() {
    qty.value++;
    console.log(qty.value);
}

function rest() {
    // Solo disminuir si qty es mayor que 1
    if (qty.value > 0) {
        qty.value--;
    }
}
</script>

<template>
    <div class="bg-purple-300 rounded max-w-80 mx-auto p-6">
        <div 
            v-if="qty > 0 || qty < 0"
            :class="{'bg-black': qty > 0, 'bg-pink-600': qty > 3}"
            class="bg-red-500 text-white size-10 rounded-full mx-auto justify-center items-center flex font-bold">
            {{ qty }}
        </div>
        <div v-else>
            nadie te visita .(
        </div>
        <div class="flex justify-between">
            <div
                @click="add"
                class="bg-blue-400 text-white rounded size-10 flex justify-center items-center font-semibold text-xl mt-2 hover:bg-blue-700 cursor-pointer duration-500">
                +
            </div>
            <div
                @click="rest"
                class="bg-blue-400 text-white rounded size-10 flex justify-center items-center font-semibold text-xl mt-2 hover:bg-blue-700 cursor-pointer">
                -
            </div>
        </div>
    </div>
</template>