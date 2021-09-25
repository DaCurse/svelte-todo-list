<script lang="ts">
  import TodoList from './TodoList.svelte';
  import type { Todo } from './types/todo.interface';
  const todos: Todo[] = [
    {
      id: 1,
      title: 'Buy eggs',
      completed: false,
    },
    {
      id: 2,
      title: 'Buy milk',
      completed: false,
    },
    {
      id: 3,
      title: 'Buy bread',
      completed: false,
    },
  ];
</script>

<main>
  <h1>Todo List</h1>
  <TodoList {todos} />
</main>
