<script setup>
import TaskComponent from './components/TaskComponent.vue';
import {ref} from 'vue';
const tareas = ref (['Estudiar', 'Sacar 5', 'Descansar',])

function deleteTask(index){
  //console.log('Borrar hijo', index)
  tareas.value.splice(index, 1)
}
</script>

<template>
<div class="bg-gray-200  mx-auto mt-12 w-96 shadow-md rounded px-4 py-3"><h1 class="text-2xl font-semibold ">Tareas</h1>
<div class="flex mt-8 mb-1">
  <input class="rounded-r-none w-4/5 h-8 px-2 py-1 border border-green-600 rounded">
  <span class="hover:bg-green-700 hover:cursor-pointer text-center text-white rounded-l-none w-1/5 h-8 text-xl rounded bg-green-600">+</span>
</div>

<TaskComponent 
v-for="(task, index) in tareas"
:key = "index"
:tarea="task"
:index="index"
@borrar-tarea="deleteTask"
/>

</div>
</template>

<style scoped>

</style>
