<script setup>
import { slide } from 'astro/virtual-modules/transitions.js';
import { ref } from 'vue';

const props = defineProps(['slides2'])

console.log(props.slides2)




let index = ref(0);

const slides = [
  { id: 1, },
  {id:2, }

];

function moveLeft() {

    index.value = index.value === 0 ? slides.length - 1 : index.value - 1;
}

function moveRight() {

    index.value = index.value === slides.length - 1 ? 0 : index.value + 1;
}
</script>

<template class="">
    <div class="bg-purple-300 rounded max-w-80 [&>div]:cursor-pointer [&>div>h1]:hover:text-blue-500 mx-auto p-6 mt-20">

        <div class="flex justify-center mb-4 ">

            <div
                @click="moveLeft"
                class="bg-blue-400 text-white rounded justify-center items-center flex p-3 cursor-pointer hover:bg-blue-700"
            >
                <
            </div>

            <div class="mx-2 text-white"
                :class="{'bg-black': index===0, 'bg-pink-600': index===1, }"     
            >
                {{ slides[index].text }}
                <div v-if="index === 0" class="text-center">
            <p>Bienvenido al primer slider.</p>
            <slot name="casita"></slot>
        </div>
        <div v-if="index === 1" class="text-center">
            <p>este es el segundo slider</p>
            <slot name="finca"></slot>

        </div>
            </div>

            <div
                @click="moveRight"
                class="bg-blue-400 text-white rounded justify-center items-center p-3 flex cursor-pointer hover:bg-blue-700"
            >
                >
            </div>
        </div>
       
        
    </div>
</template>