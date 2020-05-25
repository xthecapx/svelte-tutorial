<script>
  import Thing from "./Thing.svelte";

  let things = [
    { id: 1, color: "#0d0887" },
    { id: 2, color: "#6a00a8" },
    { id: 3, color: "#b12a90" },
    { id: 4, color: "#e16462" },
    { id: 5, color: "#fca636" }
  ];

  function handleClick() {
    things = things.slice(1);
  }
</script>

<style>
  .col {
    display: flex;
  }

  .column {
    flex: 1;
  }
</style>

<button on:click={handleClick}>Remove first thing</button>

<div class="col">
  <div class="column">
    <h1>Without ID</h1>
    <div>
      {#each things as thing}
        <Thing current={thing.color} />
      {/each}
    </div>
  </div>

  <div class="column">
    <h1>With ID</h1>
    <div>
      {#each things as thing (thing.id)}
        <Thing current={thing.color} />
      {/each}
    </div>
  </div>
</div>
