<script setup>
import HelloWorld from './components/HelloWorld.vue';
import TheWelcome from './components/TheWelcome.vue';
import increment from './components/increment.vue';
import listRendering from './components/listRendering.vue';
import watcher from './components/watcher.vue';
import props from './components/props.vue';
import emitComponent from './components/emitComponent.vue';
import { ref } from 'vue';
import slot from './components/slots.vue';

const greeting = 'Hello, Vue 3!';
const childMsg = ref('no props passed to me');
const msg = ref('slot from paranet');
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
    <div>
      <div><TheWelcome /></div>
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
    </div>
  </main>
</template>

<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
