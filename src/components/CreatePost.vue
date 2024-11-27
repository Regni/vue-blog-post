<script setup>
// Definiera props för title och body
const props = defineProps({
// Implementera props här
title: {
  type:String,
  required: true
},
body:{
  type:String,
  required: true},
isBold: Boolean

})
// Definiera dina custom events
const emit = defineEmits([
'titleChanged', 'bodyChanged','changeTitle'
])
</script>
<template>
<div class="create-post">
<!-- Skapa input för titel som:
Använder title prop som value
Emittar titleChanged vid input -->

<div class="create-post-item">
<input
type="text"
placeholder="Skriv din titel här..."
:value="title"
@input="emit('titleChanged', $event.target.value)"
><button @click ="emit('changeTitle')">{{isBold? "Normal" : " Bold "}}</button></div>
<!-- Skapa textarea för innehåll som:
Använder body prop som value
Emittar bodyChanged vid input -->
<textarea
placeholder="Skriv ditt inlägg här..."
:value="body"
@input="emit('bodyChanged', $event.target.value)"
></textarea>
</div>
</template>
<style scoped>
/* // Implementera styling här */
.create-post{
  margin: 1rem;
  display: flex;
  flex-direction: column;
  gap: 1rem
}
.create-post-item{
  display: flex;
  justify-content: center;
  
  gap: 1rem
}
</style>