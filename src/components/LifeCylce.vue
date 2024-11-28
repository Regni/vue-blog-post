<script setup>
import { onMounted, onBeforeMount, onUnmounted, ref, onUpdated } from 'vue'

const message = ref('Hello Vue!')
defineProps({isBold: Boolean})
// Implementera hooks här som loggar till konsolen
// när komponenten går genom olika stadier

onMounted(()=>{
  console.log("this is send when it was mounted")
})

onBeforeMount(()=>{console.log("this is send before this is mounted")})

onUpdated(()=>{
  console.log("this is send when it is updated")
})

onUnmounted(()=>{
  console.log("component has been unmounted")
})

</script>

<template>
  <div >
    <h2>{{ message }}</h2>
    <button @click="message = 'Updated message!'">Uppdatera meddelande</button>
  </div>
</template>