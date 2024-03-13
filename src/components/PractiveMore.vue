<script setup>
import {ref} from 'vue'

const text = ref('');
function onInput(){
  
}

const message = ref('hello world')
function updateMessage(){
  if (message.value = 'hello world'){
    message.value = 'goodbye world'
  } else {
    message.value = 'hello world'
  }
}

const count = ref(0);
function increament(){
  count.value++
}



</script>
<template>
  <div>
    <h1>Practice More</h1>
    <input type="text" @input="onInput" v-model="text" />
    <p>{{text}}</p>
    <button v-on:click="updateMessage">click me</button>
    <p>{{message}}</p>
    <button v-on:click="increament">count is: {{ count }}</button>
  </div>
</template>
