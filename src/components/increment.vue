<script setup>
import { ref } from 'vue';
const count = ref(0);

function increment() {
  count.value++;
}
// a function to get that input's value
const text = ref('');
function onInput(e) {
  text.value = e.target.value;
}

// conditional rendering
const awesome = ref(true);
function toggle() {
  awesome.value = !awesome.value;
}
</script>
<template>
  <div>
    <h1>Practice</h1>
    <button v-on:click="increment">count is:{{ count }}</button>
    <input v-model="text" @input="onInput" placeholder="type" />
    <p>{{ text }}</p>
    <button @click="toggle">Toggle</button>
    <p v-if="awesome">Vue is Awesome!🧨🎇</p>
    <p v-else>Oh no!🧨🎇</p>
  </div>
</template>
