<script setup>

import {ref} from 'vue';

    let num = ref(0);
    let time = ref(0);
    let interval;
    function add() {
        if (num.value == 0) {
            interval = setInterval(()=>{
                time.value++;
            }, 1000)
        }

        num.value++;

        if (num.value==100) {
            clearInterval(interval)
        }
    }


</script>

<template>
    <div v-on:click="add" class="bg-emerald-600 text-white py-1 px-2 rounded w-12 text-center mt-10 mx-auto transform hover:scale-125 select-none hover:cursor-pointer ease-in duration-300">
        {{ num }}
    </div>
    <div v-show="num>0">
        Time:{{ time }}
    </div>
    <div v-if="num==0">
        Dele click o le da miedo 😛
    </div>
</template>