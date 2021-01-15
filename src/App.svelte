<script>
  import BackgroundColorChange from "./components/BackgroundColorChange/BackgroundColorChange.svelte";
  import RandomQuote from "./components/RandomQuote/RandomQuote.svelte";
  import DigitalClock from "./components/DigitalClock/DigitalClock.svelte";
  import MathApp from "./components/MathApp/MathApp.svelte";
  import Todo from "./components/Todo/Todo.svelte";
  const options = [
    { id: "BackgroundColorChange", component: BackgroundColorChange },
    { id: "RandomQuote", component: RandomQuote },
    { id: "DigitalClock", component: DigitalClock },
    { id: "MathApp", component: MathApp },
    { id: "Todo", component: Todo },
  ];
  let selected = options[0];
</script>

<main>
  <!-- <BackgroundColorChange /> -->
  <!-- <RandomQuote /> -->
  <!-- <DigitalClock /> -->
  <!-- <Todo /> -->
  <section>
    <select name="choices" placeholder="Choices" bind:value={selected}>
      {#each options as opt}
        <option value={opt}>{opt.id}</option>
      {/each}
    </select>
  </section>
  <svelte:component this={selected.component} />
</main>

<style>
  section {
    display: grid;
    grid-template-columns: 1fr;
    grid-template-rows: 1fr;
  }
  select {
    margin-top: 20px;
    font-size: 2rem;
    width: 300px;
    justify-self: center;
  }
</style>
