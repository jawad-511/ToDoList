<script lang="ts">
  import dayjs from "dayjs";
  import "dayjs/locale/ar";

  dayjs.locale("ar");

  let period = dayjs().format("a") == "م" ? "مساء" : "صباح";
</script>

<header class="flex justify-between">
  <div>
    <h1 class="text-3xl">{period} الخير👋</h1>
    <h2 class="text-surface-900/50 mt-2">
      {dayjs().format("اليوم ,dddd D MMMM YYYY")}
    </h2>
  </div>
  <div class="bg-white w-16 h-16"></div>
</header>
