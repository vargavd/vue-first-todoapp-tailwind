<script setup lang="ts">
  import { ref } from 'vue';

  import TodoItem from './TodoItem.vue';

  // STATES
  let newTodoText = ref('');
  const todos = ref<{
    name: string, 
    checked: boolean
  }[]>([
    { name: 'Documentation', checked: true },
    { name: 'Tooling', checked: true },
    { name: 'Ecosystem', checked: true },
    { name: 'Community', checked: true },
    { name: 'Support Vue', checked: true },
    { name: 'Misc Todo', checked: false },
    { name: 'Learn Vue', checked: false },
  ]);

  // EVENTS
  function addTodo() {
    console.log(`Now I should add ${newTodoText.value}`);

    newTodoText.value = '';
  }
</script>

<template>
  <div class="flex align-stretch mb-5 ml-[-25px]">
    <input 
      v-model="newTodoText" 
      class="w-full rounded-md border-0 py-1.5 px-3 text-gray-900 ring-1 ring-inset ring-gray-300 placeholder:text-gray-400 focus:ring-2 focus:ring-inset focus:ring-teal-400 focus-visible:outline-none"
    >
    <button 
      @click="addTodo"
      class="flex justify-center items-center py-1 px-4 ml-2 rounded-md border border-slate-300 rounded border-solid bg-teal-400 hover:bg-teal-600 text-white text-4xl"
      >+</button>
  </div>

  <TodoItem v-for="todo in todos" :checked="todo.checked">
    <template #heading>{{ todo.name }}</template>
  </TodoItem>
</template>