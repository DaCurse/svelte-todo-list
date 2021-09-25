<script lang="ts">
  import TodoItem from './TodoItem.svelte';
  import type { Todo } from './types/todo.interface';

  export let todos: Todo[] = [];

  function deleteTodo(id: Todo['id']) {
    todos = todos.filter((todo) => todo.id !== id);
  }
</script>

<div>
  {#each todos as todo (todo.id)}
    <TodoItem {todo} />
    <button class="delete" on:click={() => deleteTodo(todo.id)}>Delete</button>
  {/each}
</div>

<style>
  .delete {
    margin-top: 5px;
  }
</style>
