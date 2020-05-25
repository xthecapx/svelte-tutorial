<script>
  let user = { loggedIn: false };
  let x = 7;

  function toggle() {
    user.loggedIn = !user.loggedIn;
  }
</script>

<div>
  {#if x > 10}
    <p>{x} is greater than 10</p>
  {:else if 5 > x}
    <p>{x} is less than 5</p>
  {:else}
    <p>{x} is between 5 and 10</p>
  {/if}
</div>

<div>
  {#if user.loggedIn}
    <button on:click={toggle}>Log out</button>
  {/if}

  {#if !user.loggedIn}
    <button on:click={toggle}>Log in</button>
  {/if}
</div>

<div>
  {#if user.loggedIn}
    <button on:click={toggle}>Log out</button>
  {:else}
    <button on:click={toggle}>Log in</button>
  {/if}
</div>
