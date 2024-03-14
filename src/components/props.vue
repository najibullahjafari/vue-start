<script setup>
const props = defineProps({
  msg: String,
});
</script>

<template>
  <h1>{{ msg || 'No props passed to me' }}</h1>
</template>
