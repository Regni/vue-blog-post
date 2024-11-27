<script setup>
// Implementera props här med validation
const props = defineProps({
title:{
 type:String,
 required: true
},
body:{
  type: String,
  required: true
},
isBold: Boolean,
isItalic: Boolean
})

</script>

<template>
   <div class="preview-post">
    <!-- Använd title prop här -->
      <h2 :class="{'bold': isBold, 'italic':isItalic}">{{ props.title }}</h2>
      <div class="post-body">
        <!-- Använd body prop här -->
         {{ props.body }}
      </div>
   </div>
</template>

<style scoped>
.preview-post {
padding: 2rem;
border: 2px solid black;
}
h2{
  font-weight: 200;
}
.bold{
  font-weight: 800;
}
.italic{
  font-style: italic;
}

</style>