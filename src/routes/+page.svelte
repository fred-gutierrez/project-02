<script>
  import CopyToClipboard from "$lib/components/CopyToClipboard.svelte";
  import ExportMarkdown from "$lib/components/ExportMarkdown.svelte";
  import TextArea from "$lib/components/TextArea.svelte";
</script>

<section class="home-container">
  <TextArea />
  <div class="grid grid-cols-2 mt-4 gap-4 px-5">
    <ExportMarkdown />
    <CopyToClipboard />
  </div>
</section>

<style lang="scss">
  .home-container {
    height: 460px;
  }
</style>
