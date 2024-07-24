<script lang="ts">
  import dayjs from "dayjs";
  import { tasks } from "$lib/stores/tasks";
  import relativeTime from "dayjs/plugin/relativeTime";
  import TaskListItems from "./TaskListItems.svelte";
  import { fade } from "svelte/transition";
  dayjs.extend(relativeTime);
</script>


    <!-- <ol transition:fade class="flex flex-col gap-2">
      <h3>المهام المتبقية:</h3>
      <TaskListItems doneTasks={true} />
    </ol>


    <ol transition:fade class="flex flex-col gap-2">
      <h3>المهام المكتملة:</h3>
    <TaskListItems doneTasks={false} />
    </ol>
   -->
    {#if $tasks.length == 0}
    <div class="flex flex-col items-center justify-center h-[50dvh]">
    <img class="h-48 w-48 text-[#141c2d]" src="coconut-tree-svgrepo-com.svg" alt="tree"/>
    <p class="font-semibold text-2xl">لايوجد مهام...</p>
  </div>
  {:else}
    {#if $tasks.filter((task) => !task.isDone).length > 0}
      <ol transition:fade class="flex flex-col gap-2">
        <h3>المهام المتبقية:</h3>
        <TaskListItems doneTasks={true} />
      </ol>
    {/if}
  
    {#if $tasks.filter((task) => task.isDone).length > 0}
      <ol transition:fade class="flex flex-col gap-2">
        <h3>المهام المكتملة:</h3>
        <TaskListItems doneTasks={false} />
      </ol>
    {/if}
  {/if}