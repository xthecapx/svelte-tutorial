<script>
  let cats = [
    { id: "J---aiyznGQ", name: "Keyboard Cat", nested: { name: "name " } },
    { id: "z_AbfPXTKms", name: "Maru", nested: { name: "name " } },
    {
      id: "OUtn3pvWmpg",
      name: "Henri The Existential Cat",
      nested: { name: "name " }
    },
    { id: "OUtn3pvWmg", name: null, nested: { name: "name " } }
  ];

  let obj = {
    foo: {
      bar: "foobar"
    }
  };

  let copy = obj;

  $: console.log(obj);
  $: console.log(copy);

  const mutate = () => {
    cats[3].name = "cristian";
    cats[3].nested.name = "cristian";

    copy.foo.bar = "cris";
  };
</script>

<!-- If the property doesn't exists, undefined is displayed -->
<!-- If the property is null, null is displayed -->
<h1>The Famous Cats of YouTube</h1>

<button on:click={mutate}>Mutate</button>

<ul>
  {#each cats as { id, name, nested }, i}
    <li>
      <a target="_blank" href="https://www.youtube.com/watch?v={id}">
        {i + 1}: {name} : {nested.name}
      </a>
    </li>
  {/each}
</ul>
