<script>
  import { textareaValue } from "$lib/stores/store";
  import { marked } from "marked";

  let markdownContent = "";
  let showEmptyMessage = false;

  $: markdownContent = marked($textareaValue);

  function exportMardown() {
    if (markdownContent.trim().length > 0) {
      const markdownText = `data:text/markdown;charset=utf-8,${encodeURIComponent(
        markdownContent,
      )}`;
      const a = document.createElement("a");
      a.href = markdownText;
      a.download = "snapnote-markdown.md";
      a.style.display = "none";
      document.body.appendChild(a);
      a.click();
      document.body.removeChild(a);
    } else {
      showEmptyMessage = true;
      setTimeout(() => {
        showEmptyMessage = false;
      }, 3000);
    }
  }
</script>

<button
  class="py-5 font-semibold rounded-lg dark:bg-neutral-600 bg-neutral-200"
  on:click={exportMardown}
>
  {#if showEmptyMessage}
    Nothing to Export
  {:else}
    Export Markdown
  {/if}
</button>
