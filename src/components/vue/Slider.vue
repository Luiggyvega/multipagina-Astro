<script setup>
import { ref } from 'vue';

const props = defineProps(['slides2'])

console.log(props.slides2)


let index = ref(0);

const slides = [
  { id: 1, text: 'slide 1' },
  { id: 2, text: 'Slide 2' },
  { id: 3, text: 'Slide 3' },
  { id: 4, text: 'Slide 4' }
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

            <div
                class="text-white size-16 text-center rounded-full mx-auto justify-center items-center flex font-bold p-6 duration-500  "
                :class="{'bg-black': index===1, 'bg-pink-600': index===2, 'bg-red-500': index===0, 'bg-blue-500':index===3}"
                
            >
                {{ slides[index].text }}
            </div>

            <div
                @click="moveRight"
                class="bg-blue-400 text-white rounded justify-center items-center p-3 flex cursor-pointer hover:bg-blue-700"
            >
                >
            </div>
        </div>
        <div v-if="index === 0" class="text-center">
            <p>Bienvenido al primer slide.</p>
            <h1>finca</h1>
        </div>
        <div v-if="index === 2" class="text-center">
            <p>este es el tercer slider</p>
            <h1>casa</h1>

        </div>
        
    </div>
</template>