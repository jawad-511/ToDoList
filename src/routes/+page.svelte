<script lang='ts'>
import Header from '$lib/Header.svelte';
import {tasks} from '$lib/stores/tasks';
    import dayjs from 'dayjs';

let title = "";
$: console.log(title);

function addTask(){
	tasks.update((currentTasks) => {
	currentTasks.push({
		title,
		assignedDate: dayjs(),
		isDone: false,
		});
		return currentTasks;
	});
}
title = "";

$: console.log($tasks);
</script>
<div class="p-16 flex flex-col gap-10">
		<Header/><!--Component-->

		

<div class="input-group input-group-divider flex justify-between">

	<input bind:value={title} class="flex-1 !bg-white" type="search" placeholder="مهمة..." />
	<button on:click={addTask} class="bg-[#141c2d] text-white">اضافة</button>
</div>
		
	
</div>