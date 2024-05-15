<script setup>
import { ref } from "vue";
    let msg = ref("Soy un mensajito")
    let cheked =ref(false);
    let data = ["hola","mundo","cruel"] 
    let filtred = data.filter((word)=>word.includes('o'))
</script>

<template>
    <input class="border " v-model="msg" :class="{'border-red-500': cheked}"/>
    <div :title="msg">
        {{ msg }}
    </div>
    <div>
        <label for="check">Seleccionado {{ cheked }}</label>
        <input type="checkbox" name="" v-model="cheked" >
    </div>

    <ul>
        <li v-for="(name, index) in data" :key="index">
        {{ (index+1) + name }}
        </li>
        <li v-for="word in filtred">{{ word }}</li>
    </ul>
</template>