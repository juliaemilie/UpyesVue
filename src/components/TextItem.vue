<script setup>
defineProps(['id'])
</script>

<template>
  <section class="my-5 text-item" :id="id">
    <h2 class="py-4">
      <slot name="heading"></slot>
    </h2>
    <slot></slot>
  </section>  
</template>
