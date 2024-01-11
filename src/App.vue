<script setup lang="ts">
import About from './components/About.vue'
import TodoList from './components/TodoList.vue'
</script>

<template>
  <header class="leading-normal mt-0 mx-auto mb-8 lg:flex place-items-center lg:pr-[calc(var(--section-gap)/2)]">
    <img 
      alt="Vue logo" 
      class="logo block my-0 ml-0 mr-8" 
      src="./assets/logo.svg" 
      width="125" 
      height="125" 
    />

    <div class="wrapper flex place-items-center flex-wrap">
      <About msg="Todo App" />
    </div>
  </header>

  <main>
    <TodoList />
  </main>
</template>

