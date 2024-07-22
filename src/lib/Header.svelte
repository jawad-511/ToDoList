<script lang="ts">
    import {
        ListBox,
        ListBoxItem,
        popup,
        type PopupSettings,
    } from "@skeletonlabs/skeleton";
  import dayjs from "dayjs";
  import "dayjs/locale/ar";

  dayjs.locale("ar");

  let period = dayjs().format("a") == "م" ? "مساء" : "صباح";

  
let comboboxValue: string ='جميع المهام';
const popupCombobox: PopupSettings = {
	event: 'click',
	target: 'popupCombobox',
	placement: 'bottom',
	closeQuery: '.listbox-item'
};
				
</script>

<header class="flex justify-between">
  <div>
    <h1 class="text-3xl">{period} الخير👋</h1>
    <h2 class="text-surface-900/50 mt-2">
      {dayjs().format("اليوم ,dddd D MMMM YYYY")}
    </h2>
  </div>
  
    
<button class="btn variant-filled w-48 justify-between" use:popup={popupCombobox}>
	<span>{comboboxValue}</span>
	<span class='text-4xl'>↓</span>
</button>


<div class="card w-48 shadow-xl py-2" data-popup="popupCombobox">
	<ListBox rounded="rounded-none">
		<ListBoxItem bind:group={comboboxValue} name="medium" value="جميع المهام">جميع المهام</ListBoxItem>
		<ListBoxItem bind:group={comboboxValue} name="medium" value="مهام اليوم">مهام اليوم</ListBoxItem>
	</ListBox>
	<div class="arrow bg-surface-100-800-token" />
</div>			
</header>
