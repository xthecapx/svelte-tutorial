<script>
  let promise = new Promise((resolve, reject) => {
      setTimeout(function() {
        resolve(10);
      }, 2000);
    });

  function handleClick() {
    promise = new Promise((resolve, reject) => {
      setTimeout(function() {
        resolve(1);
      }, 2000);
    });
  }
</script>

<button on:click={handleClick}>generate random number</button>

{#await promise}
  <p>...waiting</p>
{:then number}
  <p>The number is {number}</p>
{:catch error}
  <p style="color: red">{error.message}</p>
{/await}
