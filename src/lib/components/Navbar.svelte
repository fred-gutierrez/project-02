<script>
  import DarkModeSwitch from "./DarkModeSwitch.svelte";
</script>

<nav
  class="grid grid-cols-2 py-8 px-10 rounded-b-xl items-center dark:bg-neutral-600 dark:text-white bg-neutral-200 text-black"
>
  <div>
    <h1 class="text-2xl font-bold">
      <a href="/" class="group">
        <span class="opacity-0 group-hover:opacity-100 transition-opacity ease-in-out duration-150">/</span>SnapNote</a
      >
    </h1>
  </div>
  <div class="text-end">
    <DarkModeSwitch />
    <a href="/settings" class="ml-3"><i class="fa-regular fa-gear fa-xl"></i></a
    >
  </div>
</nav>
