<script setup>

const props = defineProps({
  title:String
})

</script>


<template>
<div class="card-container">
<header><slot name="actions"></slot> </header>
<h2>{{ props.title }}</h2>
<div>
<slot><p>this is default contenT</p></slot>

</div>
</div>

</template>

<style scoped>
.card-container{
border: solid black 2px;
margin: 2rem;
}

.content-container{
margin-top:1rem ;
}
</style>