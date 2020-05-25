<script>
  let numbers = [1, 2, 3, 4];
  const obj = { foo: { bar: 'cris' } }
  const foo = obj.foo;

  $: console.log(foo)

  function addNumber() {
    numbers = [...numbers, numbers.length + 1];
  }

  function addNumber2() {
    numbers[numbers.length] = numbers.length + 1;
  }

  function objectTest() {
    obj.bar = "baz";
    console.log({ foo })
    console.log({ obj })
  }

  $: sum = numbers.reduce((t, n) => t + n, 0);
</script>

<p>{numbers.join(' + ')} = {sum}</p>

<button on:click={addNumber}>Add a number</button>
<button on:click={addNumber2}>Add a number</button>
<button on:click={objectTest}>Obj</button>
