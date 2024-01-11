<script setup lang="ts">
  import { ref } from 'vue';

  import TodoItem from './TodoItem.vue';

  interface Todo {
    name: string, 
    checked: boolean
  };

  // STATES
  let newTodoText = ref('');
  let todos = ref<Todo[]>([
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
    todos.value.push({ name: newTodoText.value, checked: false });

    newTodoText.value = '';
  }
  function removeTodo(name: string) {
    todos.value = todos.value.filter(todo => todo.name !== name);
  }
  function checkStateChange(name: string) {
    todos.value = todos.value.map((todo:Todo) => ({...todo, checked: (todo.name === name ? !todo.checked : todo.checked)}));
  }
</script>

<template>
  <div class="flex align-stretch mb-5 ml-[-25px] gap-1">
    <input 
      v-model="newTodoText" 
      class="w-full rounded-md border-0 py-1.5 px-3 text-gray-900 ring-1 ring-inset ring-gray-300 placeholder:text-gray-400 focus:ring-2 focus:ring-inset focus:ring-teal-400 focus-visible:outline-none"
    >
    <button 
      @click="addTodo"
      class="flex justify-center items-center pt-2 pb-3 px-4 ml-2border border-slate-300 rounded border-solid bg-teal-400 hover:bg-teal-600 text-white text-4xl leading-none"
      >+</button>
  </div>

  <TodoItem v-for="todo in todos" :checked="todo.checked" :name="todo.name" :check-state-change="checkStateChange" :remove-todo="removeTodo"/>
</template>