<script>
  import Nested from "./Nested.svelte";
  import Click from "./Click.svelte";
  import Reactivity from "./Reactivity.svelte";
  import Info from "./Info.svelte";
  export let name;
  const pkg = {
    name: "svelte",
    version: 3,
    speed: "blazing",
    website: "https://svelte.dev"
  };
  let src = "https://svelte.dev/tutorial/image.gif";
  let string = `this string contains some <strong>HTML!!!</strong>`;
</script>

<style>
  p {
    color: purple;
    font-family: "Comic Sans MS", cursive;
    font-size: 2em;
  }
  main {
    text-align: center;
    padding: 1em;
    max-width: 240px;
    margin: 0 auto;
  }

  h1 {
    color: #ff3e00;
    text-transform: uppercase;
    font-size: 4em;
    font-weight: 100;
  }

  @media (min-width: 640px) {
    main {
      max-width: none;
    }
  }
</style>

<main>
  <Info {...pkg} />
  <Reactivity />
  <h1>Hello {name.toUpperCase()}!</h1>
  <Click />
  <img {src} alt="A man dances." />
  <img {src} alt="A man dances." />
  <Nested answer={42} />
  <p>
    {@html string}
  </p>
</main>
