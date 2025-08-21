<script lang="ts">
  import { writable } from 'svelte/store';

  let input = '';
  const todos = writable<string[]>([]);

  function addTodo() {
    if (input.trim()) {
      todos.update((t) => [...t, input]);
      input = '';
    }
  }
</script>

<h1 class="text-2xl font-bold">My PWA Todo</h1>

<input
  bind:value={input}
  placeholder="New todo..."
  class="border p-2"
/>
<button on:click={addTodo} class="bg-blue-500 text-white px-3 py-1">Add</button>

<ul>
  {#each $todos as todo}
    <li>{todo}</li>
  {/each}
</ul>
