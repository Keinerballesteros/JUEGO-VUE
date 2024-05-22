<script setup>

import {ref} from 'vue';


let words = ref([])
let input_Text = ref()
function addList() {
    
    words.value.push(input_Text.value)
    console.log(words)

}
</script>

<template>
    <div class="w-screen flex justify-center mt-14">
        <div class="bg-slate-400 max-w-96">
        <input v-model="input_Text" type="text" class="border-solid border-orange-200 w-9/12">
        <button @click="addList()" class="text-center text-white w-[25%] bg-slate-600">+</button>
        <div class="w-full">
            <h4 class="w-full text-center">Lista</h4>
            <p class="h-[50px] w-full" v-for="(word, index) in words">{{word}}</p>
        </div>
        </div>
    </div>

</template>