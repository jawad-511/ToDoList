<script lang="ts">
  import Header from "$lib/Header.svelte";
  import TaskInput from "$lib/TaskInput.svelte";
  import TasksList from "$lib/TasksList.svelte";
  import dayjs from "dayjs";

  import { tasks } from "$lib/stores/tasks";
 
</script>
<svelte:head>
  <title>To Do List</title>
</svelte:head>

<div
  class="p-2 sm:p-16 md:p-24 lg:p-32 flex flex-col gap-10 max-w-screen-lg mx-auto"
>
  <Header /><!--Component-->
  <TaskInput />
  <TasksList />
  
 
</div>
