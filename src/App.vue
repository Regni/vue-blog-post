<script setup>
import { ref } from 'vue';
import HelloWorld from './components/HelloWorld.vue'
import PreviewPost from './components/PreviewPost.vue';
import CreatePost from './components/CreatePost.vue';


const title = ref("this is the title")
const body = ref("lorem ipsum")
const isBold = ref(true)

const handleTitleChange = (newTitle)=>{
  title.value = newTitle

}

const  handleBodyChange = (newBody)=>{
  body.value = newBody
}

const handleTitleBold =()=>{
  isBold.value = !isBold.value
}
</script>

<template>
  <div class="app">
    <h1>Inlägg Förhandsgranskare</h1>
  <PreviewPost :isBold="isBold" :title="title" :body="body"/>
  <CreatePost 
  :isBold="isBold" 
  :title="title" 
  :body="body" 
  @bodyChanged="handleBodyChange" 
  @titleChanged="handleTitleChange"
  @changeTitle ="handleTitleBold"/>
    </div>

</template>

<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
