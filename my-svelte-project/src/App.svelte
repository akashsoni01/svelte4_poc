<script>
  import Box from "./Box.svelte";
</script>

<div class="boxes">
  <Box --color="red" />
  <Box --color="green" />
  <Box --color="blue" />
</div>

<!-- <style>
  .boxes :global(.box:nth-child(1)) {
    background-color: red;
  }

  .boxes :global(.box:nth-child(2)) {
    background-color: green;
  }

  .boxes :global(.box:nth-child(3)) {
    background-color: blue;
  }
</style> -->
