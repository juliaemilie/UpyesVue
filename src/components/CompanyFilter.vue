<script setup>
const model = defineModel()
</script>

<template>
  <span>Nach Unternehmen filtern</span> <input class="form-control" v-model="model" type="search" placeholder="z.B. Gazprom">
</template>