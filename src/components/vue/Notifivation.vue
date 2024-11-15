<script setup>
import { ref } from 'vue';
let qty = ref(0);

function add() {
    qty.value++;
    console.log(qty);
}
function rest(){
    qty.value--;

}
</script>

<template>
    <div class="bg-purple-300 rounded max-w-80 mx-auto p-6 ">
        <div 
        v-if="qty>0||qty<0"       mostrar o ocultar cosas
        :class="{'bg-orange-500':qty < 3}"
        class="bg-red-500 text-white size-8 rounded-full mx-auto justify-center items-center flex font-bold">

            {{ qty }}
        </div>
        <div class=""
        v-else="">
            nadie te visita .(
        </div>
        <div class="flex justify-between ">
            <div
            @click="add"
            class="bg-blue-400 text-white rounded size-10 flex justify-center items-center font-semibold text-xl mt-2 hover:bg-blue-700 cursor-pointer duration-500">
            +
        </div>
        <div
        @click="rest"
        class="bg-blue-400 text-white rounded size-10 flex justify-center items-center font-semibold text-xl mt-2 hover:bg-blue-700 cursor-pointer" >
            -
        </div>

        </div>
        
    </div>
</template>