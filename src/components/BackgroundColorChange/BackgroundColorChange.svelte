<script>
  let color = "#f34223";
  function changeColor() {
    color = "#" + Math.floor(Math.random() * 16777215).toString(16);
  }
</script>

<section style="background-color: {color};">
  <h1>HEX COLOR : {color}</h1>
  <button on:click={changeColor}>Change Color</button>
</section>

<style>
  section {
    display: grid;
    grid-template-columns: 1fr;
    grid-template-rows: 200px auto;
    justify-items: center;
    align-items: center;
    height: 100vh;
  }

  h1 {
    text-align: center;
    font-size: 2.8rem;
    margin: 0;
    grid-row: 1/2;
  }
  button {
    width: 300px;
    background-color: transparent;
    border: 1px solid green;
    color: #000;
    padding: 20px;
    transition: 500ms;
    font-size: 2rem;
    justify-self: center;
    align-self: start;
    grid-row: 2/3;
  }

  button:hover {
    color: #fff;
    background-color: #000;
    cursor: pointer;
  }
  button:focus {
    outline: none;
  }
</style>
