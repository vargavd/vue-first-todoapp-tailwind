<script setup lang="ts">
  defineProps<{
    name: string,
    checked: boolean,
    checkStateChange: (name: string) => void,
    removeTodo: (name: string) => void
  }>()

  import CheckIcon from './icons/IconCheck.vue'
</script>

<template>
  <div class="item flex relative lg:mt-0 lg:pt-2 lg:pb-1 lg:pl-[var(--todo-gap)] lg:mb-[calc(var(--todo-gap)*0.75)] group">
    <i 
      class="flex place-items-center place-content-center w-2 h-2 lg:left-[-26px] lg:absolute lg:rounded-[8px] lg:w-[50px] lg:h-[50px] lg:top-[calc(50%-25px)] lg:border lg:border-solid lg:border-[var(--color-border)] lg:bg-[var(--color-background)] text-[var(--color-text)]"
      v-on:click="() => checkStateChange(name)"  
    >
      <CheckIcon v-if="checked"/>
    </i>
    <div class="details flex-1 ml-4">
      <h3 class="text-xl font-medium text-[var(--color-heading)] flex gap-2 items-center">
        {{ name }}
        <svg 
          xmlns="http://www.w3.org/2000/svg" 
          height="16" 
          width="12" 
          viewBox="0 0 384 512" 
          class="hover:cursor-pointer relative top-[2.5px]"
          v-on:click="() => removeTodo(name)"
        >
          <path class="fill-red-600 hidden group-hover:inline-block" d="M345 137c9.4-9.4 9.4-24.6 0-33.9s-24.6-9.4-33.9 0l-119 119L73 103c-9.4-9.4-24.6-9.4-33.9 0s-9.4 24.6 0 33.9l119 119L39 375c-9.4 9.4-9.4 24.6 0 33.9s24.6 9.4 33.9 0l119-119L311 409c9.4 9.4 24.6 9.4 33.9 0s9.4-24.6 0-33.9l-119-119L345 137z"/>
        </svg>
      </h3>
    </div>
  </div>
</template>
