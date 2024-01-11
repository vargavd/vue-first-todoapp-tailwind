<template>
  <div class="item flex relative lg:mt-0 lg:pt-2 lg:pb-1 lg:pl-[var(--todo-gap)] lg:mb-[calc(var(--todo-gap)*0.75)]">
    <i class="flex place-items-center place-content-center w-2 h-2 lg:left-[-26px] lg:absolute lg:rounded-[8px] lg:w-[50px] lg:h-[50px] lg:top-[calc(50%-25px)] lg:border lg:border-solid lg:border-[var(--color-border)] lg:bg-[var(--color-background)] text-[var(--color-text)]">
      <slot name="icon"></slot>
    </i>
    <div class="details flex-1 ml-4">
      <h3 class="text-xl font-medium text-[var(--color-heading)]">
        <slot name="heading"></slot>
      </h3>
    </div>
  </div>
</template>
