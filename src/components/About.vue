<script setup lang="ts">
defineProps<{
  msg: string
}>()
</script>

<template>
  <div class="greetings">
    <h1 class="text-teal-500 font-bold underline font-medium text-5xl relative -top-3 text-center lg:text-left">{{ msg }}</h1>
    <h3 class="text-xl text-center lg:text-left">
      My first app with Vue and Tailwind!
    </h3>
  </div>
</template>
