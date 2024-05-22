<script setup>
import {ref} from "vue"
let options =["tijera","piedra","papel"] 
let option = ref('');
let opcion = ref('');
let answer = ref('');
function click(){
    for(let i = 0; i <= options.length; i++){
    if(opcion.value !== options[i]){
        answer.value = "Opción incorrecta"
    }
    }
    option = options[Math.floor(Math.random() * options.length)];
        if(option === opcion.value){
            answer.value = "Empate"
        }
        else if(opcion.value === "tijera" && option === "piedra" || opcion.value === "papel" && option === "tijera" || opcion.value === "piedra" && option=== "papel"){
            answer.value = "Has perdido"
        }
        else{
            answer.value = "Has ganado"
    }
}
</script>
<template>
<h2 class="text-center font-bold text-2xl text-white my-5">PIEDRA, PAPEL O TIJERA</h2>
<div class="flex justify-center items-center">
    <label class="text-white font-bold mr-2">OPCIÓN:</label>
    <input id="opcion" v-model="opcion" class="border bg-transparent rounded-lg text-white/85 w-auto h-auto p-2" type="text" placeholder="Ingrese una opcion">
    <button class="w-auto p-2 bg-white rounded-lg shadow text-black font-semibold ml-2" @click="click()">
        CLICK
    </button>
</div>
<div class="mt-2 text-white text-center w-auto p-2 ">{{ option }}</div>
<div class="mt-2 text-white text-center w-auto p-2 " >{{ answer }}</div>


</template>