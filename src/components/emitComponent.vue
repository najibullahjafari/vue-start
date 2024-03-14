<script setup>
const emit = defineEmits(['response']);

emit('response', 'hello from child component!');
</script>

<template>
  <h1>emit</h1>
</template>
