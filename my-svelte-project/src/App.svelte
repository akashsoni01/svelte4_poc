<script>
  let count = 0;

  function handleClick() {
    count += 1;
  }
  $: if (count >= 10) {
    alert("count is dangerously high!");
    count = 0;
  }
</script>

<button on:click={handleClick}>
  Clicked {count}
  {count === 1 ? "time" : "times"}
</button>
