<script>
  let setDate = "00:00:00 AM";
  import { onMount } from "svelte";
  onMount(() => {
    const interval = setInterval(() => {
      let date = new Date();
      setDate = date.toLocaleTimeString();
    }, 1000);
  });
</script>

<section>
  <h1>Your Local Time</h1>
  <h2>{setDate}</h2>
</section>

<style>
  :global(body) {
    background-color: #a8caff;
  }
  section {
    display: grid;
    grid-template-rows: 300px auto;
    grid-template-columns: 1fr;
  }
  h1 {
    font-size: 4rem;
    margin: 0;
    grid-row: 1/2;
    align-self: end;
    justify-self: center;
  }

  h2 {
    font-size: 4.5rem;
    margin: 0;
    grid-row: 2/3;
    align-self: flex-start;
    justify-self: center;
    padding: 30px;
  }
</style>
