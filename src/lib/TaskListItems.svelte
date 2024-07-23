<script lang="ts">
    import dayjs from "dayjs";
    import { tasks } from "$lib/stores/tasks";
    import relativeTime from "dayjs/plugin/relativeTime";
  
    dayjs.extend(relativeTime);

   export let doneTasks:Boolean;
  </script>

{#each $tasks as task}
    {#if !task.isDone == doneTasks}
      <li class="bg-white p-2 rounded-md flex justify-between items-center">
        <div>
          <input bind:checked={task.isDone} class="checkbox" type="checkbox" />
          <span class="mr-1">{task.title}</span>
        </div>
        <div class="flex gap-2">
          <button
            class="btn bg-[#151d2f] text-white hover:bg-slate-800 rounded-md p-2 w-40"
          >
            {dayjs(task.assignedDate).format("hh:mm")}
          </button>

          <button
            class="btn bg-[#151d2f] text-white hover:bg-slate-800 rounded-md p-2"
          >
            <svg
              class="w-6"
              xmlns="http://www.w3.org/2000/svg"
              viewBox="0 0 24 24"
              ><path
                fill="currentColor"
                d="M9.808 17h1V8h-1zm3.384 0h1V8h-1zM6 20V6H5V5h4v-.77h6V5h4v1h-1v14z"
              /></svg
            >
          </button>
        </div>
      </li>
    {/if}
  {/each}