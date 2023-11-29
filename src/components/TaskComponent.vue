<script setup>

const props =  defineProps({
    
    tarea: {

        type: String,

default: 'Tarea indefinida'
},

index: {

    type:Number

}
})

const emit = defineEmits(['borrarTarea'])

function borrarTarea(index){
    //console.log('Borrar tarea',index)
    emit('borrarTarea', index)

}


</script>

<template>
<div class="flex justify-between bg-gray-300 rounded px-4 py-1 mt-1">
  {{ props.tarea }}
  <span class="px-2 hover:bg-red-700 hover:cursor-pointer text-center text-white  h-6  rounded bg-red-400 "
  @click=borrarTarea(props.index)
  >
    X
  </span>



</div>





</template>