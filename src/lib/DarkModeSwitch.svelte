<script>
  let darkMode = false;

  function toggleDarkMode() {
    darkMode = !darkMode;

    if (darkMode) {
      document.documentElement.classList.add("dark");
    } else {
      document.documentElement.classList.remove("dark");
    }
  }
</script>

<button on:click={toggleDarkMode}>
  {#if darkMode}
    <i class="fa-regular fa-space-station-moon-construction fa-xl"></i>
  {:else}
    <i class="fa-sharp fa-regular fa-sun-bright fa-xl"></i>
  {/if}
</button>
