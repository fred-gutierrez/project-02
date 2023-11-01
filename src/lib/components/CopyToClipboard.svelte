<script>
  import { textareaValue } from "$lib/stores/store";
  let copyDone = "";
  let copyError = "";

  function copyToClipboard() {
    const textToCopy = $textareaValue;

    if (textToCopy.trim().length === 0) {
      copyError = "No Content to Copy";
      copyDone = "";
      setTimeout(() => {
        copyError = "";
      }, 3000);
      return;
    }

    navigator.clipboard
      .writeText($textareaValue)
      .then(() => {
        copyDone = "Copied to Clipboard!";
        copyError = "";
        setTimeout(() => {
          copyDone = "";
        }, 3000);
      })
      .catch((error) => {
        copyError = "Copy to Clipboard failed " + error;
        copyDone = "";
        setTimeout(() => {
          copyError = "";
        }, 3000);
      });
  }
</script>

<button
  class="py-5 font-semibold rounded-lg dark:bg-neutral-600 bg-neutral-200"
  on:click={copyToClipboard}
>
  {#if copyDone}
    {copyDone}
  {:else if copyError}
    {copyError}
  {:else}
    Copy to Clipboard
  {/if}
</button>
