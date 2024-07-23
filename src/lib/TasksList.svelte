<script lang="ts">
  import dayjs from "dayjs";
  import { tasks } from "$lib/stores/tasks";
  import relativeTime from "dayjs/plugin/relativeTime";
import TaskListItems from "./TaskListItems.svelte";
  dayjs.extend(relativeTime);
</script>

<ol class="flex flex-col gap-2">
  <h3>المهام المتبقية:</h3>
  <TaskListItems doneTasks = {true} />
</ol>

<ol class="flex flex-col gap-2">
    <h3>المهام المكتملة:</h3>
    <TaskListItems doneTasks = {false}/>
  
</ol>
