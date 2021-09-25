<script lang="ts">
  import type { Todo } from './types/todo.interface';

  export let todo: Todo;
  let isEditing: boolean = false;

  function handleClick() {
    if (todo.completed) {
      return;
    }
    isEditing = true;
  }

  function handleBlur() {
    isEditing = false;
  }

  function select(el: HTMLInputElement) {
    el.select();
  }
</script>

<div>
  <input type="checkbox" bind:checked={todo.completed} />
  {#if isEditing}
    <input
      type="text"
      bind:value={todo.title}
      on:blur={handleBlur}
      use:select
    />
  {:else}
    <div
      class="content"
      class:completed={todo.completed}
      on:click={handleClick}
    >
      {todo.title}
    </div>
  {/if}
</div>

<style>
  .content {
    cursor: pointer;
    display: inline-block;
    margin-bottom: 2px;
  }
  .content.completed {
    cursor: default;
    text-decoration: line-through;
  }
</style>
