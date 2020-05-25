<script>
  let count = 0;
  $: doubled = count * 2;
  $: if (count >= 10) {
    alert(`count is dangerously high!`);
    count = 9;
  }

  function handleClick() {
    // event handler code goes here
    count++;
  }
</script>

<div>
  <p>{count} doubled is {doubled}</p>
  <button on:click={handleClick}>
    Clicked {count} {count === 1 ? 'time' : 'times'}
  </button>
</div>
