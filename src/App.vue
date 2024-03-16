<script setup>
import HelloWorld from './components/HelloWorld.vue';
import TheWelcome from './components/TheWelcome.vue';
import increment from './components/increment.vue';
import listRendering from './components/listRendering.vue';
import watcher from './components/watcher.vue';
import props from './components/props.vue';
import emitComponent from './components/emitComponent.vue';
import { ref } from 'vue';
import optionapiexample from './components/optionapi/optionapiexample.vue';

const greeting = 'Hello, Vue 3!';
const childMsg = ref('no props passed to me');
const msg = ref('slot from parent');
</script>

<template>
  <header>
    <img
      alt="Vue logo"
      class="logo"
      src="./assets/logo.svg"
      width="125"
      height="125"
    />

    <div class="wrapper">
      <HelloWorld msg="You did it!" />
    </div>
  </header>

  <main>
    <div class="practice">
      <div><increment /></div>
      <div><listRendering /></div>
      <div><watcher /></div>
      <div></div>
      <div><props :msg="greeting" /></div>
      <div>
        <emitComponent @response="(msg) => (childMsg = msg)" />
        <p>{{ childMsg }}</p>
      </div>
      <slots>{{ msg }}</slots>
      <div><optionapiexample /></div>
    </div>
  </main>
</template>
<style>
.practice {
  border: 1px solid black;
  padding: 10px;
  border-radius: 10px;
  box-shadow: 2px 2px 5px 2px #888888;
}
</style>
