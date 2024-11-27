<script setup>
import { ref} from 'vue';
defineProps({
  isActive:Boolean
})

const emit = defineEmits(['clickBtn'])
const handleClick=()=>{
 emit('clickBtn')
}
</script>



<template>
<button @click="handleClick" :class="{'active':isActive}">
  <slot>something here</slot>
</button>

</template>



<style scoped>
button{
  width: 5rem;
}
.active{
  background-color: green
}
</style>