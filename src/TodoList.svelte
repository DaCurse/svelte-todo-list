<script lang="ts">
  import TodoItem from './TodoItem.svelte';
  import type { Todo } from './types/todo.interface';

  export let todos: Todo[] = [];
</script>

{#each todos as todo (todo.id)}
  <TodoItem {todo} />
{/each}
