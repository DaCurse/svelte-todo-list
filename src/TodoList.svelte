<script lang="ts">
  import TodoItem from './TodoItem.svelte';
  import type { Todo } from './types/todo.interface';

  export let todos: Todo[] = [];
</script>

<ul>
  {#each todos as todo (todo.id)}
    <li><TodoItem {todo} /></li>
  {/each}
</ul>

<style>
  ul {
    list-style: none;
  }
</style>
