<script>
  import Navbar from "$lib/Navbar.svelte";
  import "../app.css";
</script>

<svelte:head
  ><title>SnapNote</title><meta
    name="description"
    content="This is a very nice and quick note taking extension!"
  /></svelte:head
>

<section class="app">
  <div class="dark:bg-neutral-700 dark:text-white bg-neutral-200 text-black">
    <slot />
  </div>
  <Navbar />
</section>

<style lang="scss">
  @import url("https://site-assets.fontawesome.com/releases/v6.4.2/css/all.css");
  @import url("https://site-assets.fontawesome.com/releases/v6.4.2/css/sharp-solid.css");
  @import url("https://site-assets.fontawesome.com/releases/v6.4.2/css/sharp-regular.css");
  @import url("https://site-assets.fontawesome.com/releases/v6.4.2/css/sharp-light.css");

  .app {
    width: 500px;
  }
</style>
