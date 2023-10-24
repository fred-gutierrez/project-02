<script>
  import { browser } from "$app/environment";
  import { onMount } from "svelte";

  let darkMode = false;

  if (browser) {
    const storedDarkMode = localStorage.getItem("darkMode");
    darkMode = storedDarkMode ? JSON.parse(storedDarkMode) : false;
  }

  function toggleDarkMode() {
    darkMode = !darkMode;

    if (darkMode) {
      document.documentElement.classList.add("dark");
    } else {
      document.documentElement.classList.remove("dark");
    }

    if (browser) {
      localStorage.setItem("darkMode", JSON.stringify(darkMode));
    }
  }

  onMount(() => {
    if (darkMode) {
      document.documentElement.classList.add("dark");
    }
  });
</script>

<button on:click={toggleDarkMode}>
  {#if darkMode}
    <i class="fa-regular fa-space-station-moon-construction fa-xl"></i>
  {:else}
    <i class="fa-sharp fa-regular fa-sun-bright fa-xl"></i>
  {/if}
</button>
