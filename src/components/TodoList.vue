<script setup lang="ts">
  import { ref } from 'vue';

  import TodoItem from './TodoItem.vue'
  import CheckIcon from './icons/IconCheck.vue'

  // STATES
  let newTodoText = ref('');

  // EVENTS
  function addTodo() {
    console.log(`Now I should add ${newTodoText.value}`);

    newTodoText.value = '';
  }
</script>

<template>
  <div class="add-todo">
    <input v-model="newTodoText">
    <button @click="addTodo">+</button>
  </div>

  <TodoItem>
    <template #icon>
      <CheckIcon />
    </template>
    <template #heading>Documentation</template>

    Vue’s
    <a href="https://vuejs.org/" target="_blank" rel="noopener">official documentation</a>
    provides you with all information you need to get started.
  </TodoItem>

  <TodoItem>
    <template #icon>
      <CheckIcon />
    </template>
    <template #heading>Tooling</template>

    More instructions are available in <code>README.md</code>.
  </TodoItem>

  <TodoItem>
    <template #icon>
      <CheckIcon />
    </template>
    <template #heading>Ecosystem</template>

    Get official tools and libraries for your project:
    <a href="https://pinia.vuejs.org/" target="_blank" rel="noopener">Pinia</a>,
    <a href="https://router.vuejs.org/" target="_blank" rel="noopener">Vue Router</a>,
    <a href="https://test-utils.vuejs.org/" target="_blank" rel="noopener">Vue Test Utils</a>, and
    <a href="https://github.com/vuejs/devtools" target="_blank" rel="noopener">Vue Dev Tools</a>. If
    you need more resources, we suggest paying
    <a href="https://github.com/vuejs/awesome-vue" target="_blank" rel="noopener">Awesome Vue</a>
    a visit.
  </TodoItem>

  <TodoItem>
    <template #icon>
      <CheckIcon />
    </template>
    <template #heading>Community</template>

    Got stuck? Ask your question on
    <a href="https://chat.vuejs.org" target="_blank" rel="noopener">Vue Land</a>, our official
    Discord server, or
    <a href="https://stackoverflow.com/questions/tagged/vue.js" target="_blank" rel="noopener"
      >StackOverflow</a
    >. You should also subscribe to
    <a href="https://news.vuejs.org" target="_blank" rel="noopener">our mailing list</a> and follow
    the official
    <a href="https://twitter.com/vuejs" target="_blank" rel="noopener">@vuejs</a>
    twitter account for latest news in the Vue world.
  </TodoItem>

  <TodoItem>
    <template #icon>
      <CheckIcon />
    </template>
    <template #heading>Support Vue</template>

    As an independent project, Vue relies on community backing for its sustainability. You can help
    us by
    <a href="https://vuejs.org/sponsor/" target="_blank" rel="noopener">becoming a sponsor</a>.
  </TodoItem>
</template>

<style>
  .add-todo {
    display: flex;
    margin: 20px 20px 20px -25px;
  }
</style>