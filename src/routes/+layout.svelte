<script lang="ts">
  import favicon from "$lib/assets/favicon.svg";
  import AppSidebar from "$lib/components/app-sidebar.svelte";
  import * as Sidebar from "$lib/components/ui/sidebar/index.js";

  let { children } = $props();
  import "../app.css";
</script>

<svelte:head>
  <link rel="icon" href={favicon} />
</svelte:head>

<Sidebar.Provider>
  <AppSidebar />
  <main class="p-5">
    <Sidebar.Trigger class="hidden md:block"/>
    {@render children?.()}
  </main>
</Sidebar.Provider>
