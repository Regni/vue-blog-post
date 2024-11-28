<script setup>
import { ref } from 'vue';
import HelloWorld from './components/HelloWorld.vue'
import PreviewPost from './components/PreviewPost.vue';
import CreatePost from './components/CreatePost.vue';
import BaseCard from './components/BaseCard.vue';
import BaseButton from './components/BaseButton.vue';
import LifeCylce from './components/LifeCylce.vue';


const title = ref("this is the title")
const body = ref("lorem ipsum")
const isBold = ref(true)
const isItalic = ref(false)

const handleTitleChange = (newTitle)=>{
  title.value = newTitle

}

const  handleBodyChange = (newBody)=>{
  body.value = newBody
}

const handleTitleBold =()=>{
  isBold.value = !isBold.value
}

const handleTitleItalic =()=>{
  isItalic.value=!isItalic.value
}
</script>

<template>
<div class="app">
  <h1>Lifecycle Hooks</h1>
  <LifeCylce :isBold="isBold"  v-if="isBold"></LifeCylce>
</div>


  <div class="app">
    <h1>Inlägg Förhandsgranskare</h1>
  <PreviewPost :isBold="isBold" :title="title" :body="body" :isItalic="isItalic"/>
  <CreatePost 
  :isBold="isBold" 
  :title="title" 
  :body="body"
  :isItalic="isItalic"
  @bodyChanged="handleBodyChange" 
  @titleChanged="handleTitleChange"
  @changeTitleBold ="handleTitleBold"
  @changeTitleItalic="handleTitleItalic"/>
  
    </div>
<BaseCard :title="'Preview post'"><PreviewPost :isBold="isBold" :title="title" :body="body" :isItalic="isItalic"/></BaseCard>
<BaseCard :title="'Preview post'"><CreatePost 
  :isBold="isBold" 
  :title="title" 
  :body="body"
  :isItalic="isItalic"
  @bodyChanged="handleBodyChange" 
  @titleChanged="handleTitleChange"
  @changeTitleBold ="handleTitleBold"
  @changeTitleItalic="handleTitleItalic"/><template #actions><BaseButton :isActive="isBold" @clickBtn="handleTitleBold">B</BaseButton>
    <BaseButton :isActive="isItalic" @clickBtn="handleTitleItalic">I</BaseButton></template></BaseCard>
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
