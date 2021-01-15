<script>
  let num1 = 0,
    num2 = 0,
    answer = 0;
  import { onMount } from "svelte";

  function getRandom() {
    return Math.floor(Math.random() * 100);
  }

  function setNum() {
    num1 = getRandom();
    num2 = getRandom();
  }

  onMount(() => {
    setNum();
  });

  function checkAnswer() {
    if (num1 + num2 == answer) {
      alert("Win");
      setNum();
    } else {
      alert("Loose");

      setNum();
    }
  }
</script>

<section>
  <h1>{num1} <span> + </span></h1>
  <h1>{num2} <span> = </span></h1>
  <input type="number" name="answer" bind:value={answer} />
  <button on:click={checkAnswer}>Check</button>
</section>

<style>
  :global(body) {
    background-color: coral;
  }
  section {
    margin: 10% auto;
    width: 50%;
    padding: 10px;
  }

  h1 {
    font-size: 4rem;
    margin: 0;
    padding-top: 20px;
    display: inline-block;
    text-align: center;
  }

  input {
    font-size: 4rem;
    width: 300px;
  }

  button {
    margin: 20px;
    display: inline;
    font-size: 2rem;
    background-color: brown;
    color: #fff;
    border: none;
    padding: 10px;
    border-radius: 10px;
  }
</style>
