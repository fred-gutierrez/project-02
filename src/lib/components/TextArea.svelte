<script>
  import { textareaValue } from "$lib/stores/store";

  let currentValue = "";

  textareaValue.subscribe((value) => {
    currentValue = value;
  });

  function handleTextareaInput(event) {
    textareaValue.set(event.target.value);
  }
</script>

<div class="flex justify-center">
  <textarea
    placeholder="Let’s start typing! Press ‘/’ for commands..."
    class="p-3 h-96 w-11/12 overflow-y-auto rounded-xl dark:bg-neutral-600 bg-neutral-200 outline-none"
    on:input={handleTextareaInput}
    bind:value={currentValue}
  />
</div>
