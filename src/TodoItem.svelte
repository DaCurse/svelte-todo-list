<script lang="ts">
  import type { Todo } from './types/todo.interface';

  export let todo: Todo;
</script>

<div>
  <input type="checkbox" bind:checked={todo.completed} />
  <p class:completed={todo.completed}>{todo.title}</p>
</div>

<style>
  p {
    display: inline-block;
  }

  .completed {
    text-decoration: line-through;
  }
</style>
