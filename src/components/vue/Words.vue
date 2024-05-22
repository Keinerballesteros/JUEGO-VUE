<script setup>
    import { ref } from 'vue'
    let words = ref([])
    let input_text = ref()

    function addList(){
        words.value.push(input_text.value)
    }

</script>
<template>
    <div class="w-screen justify-center p-2 mt-2">
        <h2 class="font-semibold text-2xl text-center text-white ">TAREAS</h2>
        <div class="flex flex-row mt-5 justify-center">
            <input class="w-auto p-2 bg-transparent text-white font-semibold" placeholder="Ingrese una tarea" type="text" v-model="input_text">
            <button class="w-auto p-3 bg-white text-black" @click="addList()">Añadir</button>
        </div>
        <div class="mt-4">
            <h2 class="font-semibold text-xl text-center text-white/85">LISTA DE TAREAS</h2>
            <p class="font-medium text-white text-lg text-center" v-for="(word, index) in words" :class="{'bg-black': index % 2 !== 0, 'bg-blue-500/60':index % 2 === 0  }" >{{ word }} </p>
        </div>
    </div>
</template>