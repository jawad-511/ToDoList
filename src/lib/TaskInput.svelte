<script lang="ts">
  import { tasks } from "$lib/stores/tasks";
  import dayjs from "dayjs";
    import AddTask from "./icons/AddTask.svelte";
  

  let title = "";
  let dateTime = dayjs().format('YYYY-MM-DDThh:mm');

  $: console.log(dateTime);

  function addTask() {
    tasks.update((currentTasks) => {
      currentTasks.push({
        title,
        assignedDate: dateTime,
        isDone: false,
      });
      return currentTasks.sort((a:Task , b:Task) =>{
        return dayjs(a.assignedDate).unix() - dayjs(b.assignedDate).unix();
      });
    });
    title = "";
  }
</script>

<div
  class="input-group input-group-divider flex justify-between flex-col sm:flex-row !bg-white rounded-lg"
>
  <input
    bind:value={title}
    class="flex-1"
    type="search"
    placeholder="مهمة..."
  />
  <input
    bind:value={dateTime}
    class="input sm:w-fit"
    title="Input (datetime-local)"
    type="datetime-local"
  />
  <button on:click={addTask} class="bg-[#141c2d] text-white p-2">
    <span class="mx-auto">
      <AddTask />
  </span>
</button>
</div>
