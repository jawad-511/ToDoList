<script lang='ts'>
import Header from '$lib/Header.svelte';
import {name} from '$lib/stores/name';

function updateName(name : string): string {
	return name + '1';
}

name.update(updateName);
console.log($name);

</script>
<div class="p-16 flex flex-col gap-10">
		<Header/><!--Component-->

		

<div class="input-group input-group-divider flex justify-between">

	<input class="flex-1 !bg-white" type="search" placeholder="مهمة..." />
	<button class="bg-[#141c2d] text-white">اضافة</button>
</div>
		
	
</div>