<script lang="ts">
  import TodoItem from './TodoItem.svelte';
  import type { Todo } from './types/todo.interface';

  export let todos: Todo[] = [];
  let newTodo: string = '';

  function handleSubmit(e) {
    todos = [
      ...todos,
      {
        id: todos.length + 1,
        title: newTodo,
        completed: false,
      },
    ];

    e.target.reset();
  }

  function deleteTodo(id: Todo['id']) {
    todos = todos.filter((todo) => todo.id !== id);
  }
</script>

<div>
  {#each todos as todo (todo.id)}
    <TodoItem {todo} />
    <button class="delete" on:click={() => deleteTodo(todo.id)}>Delete</button>
  {/each}

  <form on:submit|preventDefault={handleSubmit}>
    <input type="text" bind:value={newTodo} placeholder="Add new item..." />
    <input type="submit" value="Add" />
  </form>
</div>

<style>
  .delete {
    margin-top: 5px;
  }

  form {
    margin-top: 1rem;
  }
</style>
